# Custom Import App

> title: Create a custom import application with your logic to upload your data to Supervisely platform.

> description:
> This guide is for developers who want to create a custom import application with their own logic to upload data.
> 📚 You can find the example of the import app in the GitHub [repository](https://github.com/supervisely-ecosystem/template-import-app)

> Here is ready-to-use script with the example of the import app that you can run in your local environment to upload your dataset to Supervisely platform.
> Use the `sly.app.Import` class from Supervisely SDK and reimplement the `process` method. Prepare other necessary files for the app to work correctly, learn more about in the [complete guidance](https://developer.supervisely.com/app-development/create-import-app/overview).

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
