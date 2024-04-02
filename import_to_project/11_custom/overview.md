# Custom Import App

> description: Create a custom import application with your logic to upload your data to Supervisely platform.

ℹ️ This guide is for developers who want to create a custom import application with their own logic to upload data.

> Before you start, read our [from script to supervisely app](https://developer.supervisely.com/app-development/basics/from-script-to-supervisely-app) guide if you are unfamiliar with the file structure of a Supervisely app repository because it addresses the majority of the potential questions.

Supervisely provides [complete guidance](https://developer.supervisely.com/app-development/create-import-app/overview) with 3 options to create an import application:

    - From template - simple (recommended ✅)
    - From scratch - simple
    - From scratch GUI - advanced

We recommend using the import template for creating custom import applications using class `sly.app.Import` from Supervisely SDK. It is the easiest way to create import app with a convenient GUI. It is designed to speed up and simplify the development of import apps.

📚 You can find the example of the import app in the GitHub [repository](https://github.com/supervisely-ecosystem/template-import-app)

# How to create a custom import application:

1. Fork and Clone the [template-import-app](https://github.com/supervisely-ecosystem/template-import-app)

2. Open the cloned repository in your favorite IDE

3. Set up the working environment - here is a link with a description of the steps.

4. Open `local.env` files and set up environment variables by inserting your values here for debugging.

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

        # ... your logic here

        return project_id # ⬅️ return project_id


app = MyImport()
app.run()
```

6. Run the application locally to test your logic.
