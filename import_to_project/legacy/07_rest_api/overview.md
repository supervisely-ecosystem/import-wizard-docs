# REST API

> title: Use the REST API to interact with Supervisely platform.

> description:
> Use the REST API endpoints to programmatically interact with Supervisely. You can use it to do almost anything you can do through the web interface.
> Here is an example of how to list all projects in a workspace using the REST API:

    ```bash
    curl -H "x-api-key: <your-token-here>" -H "Content-Type: application/json" --data '{"workspaceId": <your-workspace-id>}' https://app.supervisely.com/public/api/v3/projects.list
    ```

> More information about the REST API can be found in the overview and the [API Documentation](https://api.docs.supervisely.com/).
