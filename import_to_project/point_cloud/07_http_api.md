# HTTP API

### Description

Use API to interact with Supervisely to do almost anything you can do through the web interface.

### Overview

Everything you do visually in the UI can also be accomplished through the API to programmatically interact with Supervisely. You can customize any action using over 300 methods available. Detailed documentation for these methods can be found in our <a href="https://api.docs.supervisely.com/" target="_blank">Supervisely REST API Docs</a>.

cURL Example to get dataset info:

```bash
curl -H "x-api-key: <your-token-here>" -H "Content-Type: application/json" --data '{"id": <your-dataset-id>}' https://app.supervisely.com/public/api/v3/datasets.info
```
