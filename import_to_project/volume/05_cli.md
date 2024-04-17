# CLI

### Description

Upload data from your computer using CLI.

### Overview

Import data into Supervisely using your computer terminal or by incorporating it into your own shell scripts. Useful for large datasets or automatization.

**1. Supervisely SDK CLI**

First of all, you need to install it:

```bash
pip3 install –upgrade supervisely
```

Then upload your local project by the single command:

```bash
supervisely project upload -s <source-local> -id <workspace-id> -n <project-name>
```

To learn more about Supervisely SDK CLI click <a href="https://developer.supervisely.com/getting-started/command-line-interface/sdk-cli" target="_blank">here</a>.

**2. Enterprise CLI Tool**

Installation:

```bash
sudo curl -fsSL https://config.enterprise.supervise.ly/cli -o /usr/local/bin/supervisely && sudo chmod +x /usr/local/bin/supervisely
```

Run this single command to upload your local project:

```bash
supervisely instance $entity_type upload-project -p <local_path> -n <project_name> -tid <team_id> -wid <workspace_id>
```

To learn more about Enterprise CLI Tool click <a href="https://developer.supervisely.com/getting-started/command-line-interface/cli-tool" target="_blank">here</a>.
