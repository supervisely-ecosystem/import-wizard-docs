# REST API

> description: Use the REST API to interact with Supervisely platform.

The REST API is a set of endpoints that allow you to programmatically interact with Supervisely. You can use it to do almost anything you can do through the web interface. For example, you can create and manage projects, upload images, create datasets, and much more.

Supervisely has a rich [HTTP REST API](https://api.docs.supervisely.com/) that covers basically every action, you can do manually. You can use any programming language and any development environment to extend and customize your Supervisely experience.

Find the full list of available endpoints in the [API Documentation](https://api.docs.supervisely.com/).

> ℹ️ For Python developers, we recommend using our Python SDK because it wraps up all API methods and can save you a lot of time with built-in error handling, network re-connection, response validation, request pagination, and so on.

## Authentication

The client has to send authentication header to endpoints. Please obtain your token by selecting `Account Settings` -> `API Tokens` in [user menu](https://app.supervisely.com/user/settings/tokens). Provide this token in every request in header `x-api-key.`

## Making HTTP requests

Please follow these rules working with Supervisely API:

- HTTP methods (like `GET` or `POST`) mentioned here are totally optionally. We accept any method: i.e. you can send every request with POST.
- When sending data, you must explicitly set the Content-type HTTP header to `application/json`. We won't interpret your POST body as such without it.

## Example

cURL Example (replace `<your-token-here>` with your actual token) and `<your-workspace-id>` with your actual workspace id)

```bash
curl -H "x-api-key: <your-token-here>" -H "Content-Type: application/json" --data '{"workspaceId": <your-workspace-id>}' https://app.supervisely.com/public/api/v3/projects.list
```
