# Python

description: >-
Use Supervisely SDK to upload your local data to Supervisely platform.

Learn more about the Supervisely SDK [here](https://developer.supervisely.com/getting-started/python-sdk-tutorials).

## Ready-to-use Python script

Use the Supervisely SDK to upload your local data to the Supervisely platform. Here is a ready-to-use Python script that you can run in your local environment to upload your dataset to Supervisely platform:

```python
import os

from dotenv import load_dotenv

import supervisely as sly

if sly.is_development():
    load_dotenv(os.path.expanduser("~/supervisely.env"))

api = sly.Api()

# Set your project type and source directory with your local dataset
PROJECT_TYPE = sly.ProjectType.IMAGES
SRC_DIR = "path/to/your/local/dataset"

workspace_id = sly.env.workspace_id()
project = api.project.create(workspace_id, "My project", PROJECT_TYPE, change_name_if_conflict=True)
dataset = api.dataset.create(project.id, "My dataset")

# initialize ImportManager
importer = sly.ImportManager(SRC_DIR, PROJECT_TYPE)

# upload dataset
importer.upload_dataset(dataset.id)

print("Success! Your dataset has been uploaded.")
```

## Prerequisites

Before running the script, make sure you have completed the following steps:

**0. Python version**

You should use 🐍 **Python 3.8 or greater**, which can be installed either through the [Anaconda](https://www.anaconda.com/products/distribution) package manager, [Homebrew](https://brew.sh/), or the [Python website](https://www.python.org/downloads/mac-osx/).

**1. Create a virtual environment**

It is recommended to create a virtual environment to install the required packages. Run the following commands in your terminal from the parent directory of your project folder:

```bash
python3 -m venv venv
source venv/bin/activate
```

**2. Install Supervisely package**

To use Supervisely SDK you first need to install the latest Supervisely package:

_(venv)_

```bash
pip3 install supervisely
```

After that, you will be able to use Supervisely SDK. Learn more about SDK installation [here](https://developer.supervisely.com/getting-started/installation).

**3. Set up authentication**

Save the secret `.env` file to `~/supervisely.env` with your credentials. [Learn about the basics of authentication in Supervisely](https://developer.supervisely.com/getting-started/basics-of-authentication).

The content of this file will look something like this:

```python
SERVER_ADDRESS="https://app.supervise.ly"
API_TOKEN="4r47N.....blablabla......xaTatb"
```

**4. Prepare env variables**

Save the `local.env` file to the directory with your python srcipt. [Learn about the Environment variables in Supervisely](https://developer.supervisely.com/getting-started/environment-variables).

The content of this file will look something like this:

```python
WORKSPACE_ID=942
TEAM_ID=506
```
