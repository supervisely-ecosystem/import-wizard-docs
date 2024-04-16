# Python

> title: Use Python SDK to upload your local data to Supervisely platform

> description:
> Use Python SDK to upload your local data to Supervisely platform. Learn more about the Supervisely SDK in out [developer portal](https://developer.supervisely.com/getting-started/python-sdk-tutorials).
> Here is a ready-to-use Python script that you can run in your local environment to upload your dataset to Supervisely platform:

    ```python
    import os

    from dotenv import load_dotenv

    import supervisely as sly

    if sly.is_development():
        load_dotenv(os.path.expanduser("~/supervisely.env"))

    api = sly.Api()

    # Set your project type and source directory with your local dataset
    PROJECT_TYPE = sly.ProjectType.IMAGES       # ⬅️ Set your project type
    SRC_DIR = "path/to/your/local/dataset"      # ⬅️ Set your source directory
    TEAM_ID = 506                               # ⬅️ Set your team ID
    WORKSPACE_ID = 942                          # ⬅️ Set your workspace ID

    project = api.project.create(WORKSPACE_ID, "My project", PROJECT_TYPE, change_name_if_conflict=True)
    dataset = api.dataset.create(project.id, "My dataset")

    # initialize ImportManager
    importer = sly.ImportManager(SRC_DIR, PROJECT_TYPE, TEAM_ID)

    # upload dataset
    importer.upload_dataset(dataset.id)

    print("✅ Your dataset has been uploaded.")
    ```
