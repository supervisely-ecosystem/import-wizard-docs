# Custom Import App

> description: Create a custom import application with your logic to upload your data to Supervisely platform.

ℹ️ This guide is for developers who want to create a custom import application with their own logic to upload data.

> Before you start, read our [from script to supervisely app](https://developer.supervisely.com/app-development/basics/from-script-to-supervisely-app) guide if you are unfamiliar with the file structure of a Supervisely app repository because it addresses the majority of the potential questions.

Supervisely provides 3 options to create an import application:

    - From template - simple (recommended ✅)
    - From scratch - simple
    - From scratch GUI - advanced

In this guide, we will show you the easiest way to create an import application – from template. Learn more about the other options in the [complete guidance](https://developer.supervisely.com/app-development/create-import-app/overview).

### What does it mean to create an import application from a template?

It means using the class `sly.app.Import` from Supervisely SDK. Only thing you need to do is to reimplement the `process` method.

The template will take care of the rest:

    - It will create a GUI for you.
    - It will handle the upload process.
    - It will provide you with the necessary variables in the `context` object.

It is the easiest way to create import app with a convenient GUI. It is designed to speed up and simplify the development of import apps.

📚 You can find the example of the import app in the GitHub [repository](https://github.com/supervisely-ecosystem/template-import-app)

### How to create a custom import application:

1. Fork and Clone the [template-import-app](https://github.com/supervisely-ecosystem/template-import-app)

2. Open the cloned repository in your favorite IDE

```bash
git clone <your_forked_repo>
cd template-import-app
code .
```

3. Set up the working virtual environment and install the required packages.

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

4. Open `local.env` files and set up environment variables by inserting your values here for debugging.

```env
TEAM_ID=8                      # ⬅️ change it to your team ID
WORKSPACE_ID=349               # ⬅️ change it to your workspace ID
SLY_APP_DATA_DIR="input/"      # ⬅️ path to directory for local debugging

# Optional. Specify following variables if you want to import data to existing:
# PROJECT_ID=20811             # ⬅️ put your value here
# DATASET_ID=64686             # ⬅️ put your value here | requires PROJECT_ID
```

5. Open `main.py` and write your logic to upload data to Supervisely platform.

```python
import os

import supervisely as sly

from dotenv import load_dotenv

# load ENV variables for debug, has no effect in production
if sly.is_production():
    load_dotenv("advanced.env")
    load_dotenv(os.path.expanduser("~/supervisely.env"))
else:
    load_dotenv("local.env")
    load_dotenv(os.path.expanduser("~/supervisely.env"))


class MyImport(sly.app.Import):
    def process(self, context: sly.app.Import.Context):
        # create api object to communicate with Supervisely Server
        api = sly.Api.from_env()

        # get or create project
        project_id = context.project_id
        if project_id is None:
            project = api.project.create(
                workspace_id=context.workspace_id,
                name=context.project_name or "My Project",
                change_name_if_conflict=True,
            )
            project_id = project.id

        # get or create dataset
        dataset_id = context.dataset_id
        if dataset_id is None:
            dataset = api.dataset.create(
                project_id=project_id, name="ds0", change_name_if_conflict=True
            )
            dataset_id = dataset.id

        # * your logic here:
        # ...

        return project_id # ℹ️ return project_id


app = MyImport()
app.run()
```

6. Run the application locally to test your logic.
