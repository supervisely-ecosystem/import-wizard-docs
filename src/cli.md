# Command Line Interface (CLI)

description: >-
Use CLI to upload your data right inside your console locally to Supervisely platform.

## Prerequisites

**1. Install Supervisely package**

To use CLI you first need to install the latest Supervisely package on your system:

```bash
pip3 install --upgrade supervisely
```

After that, you will be able to use CLI. Learn more about SDK installation [here](https://developer.supervisely.com/getting-started/installation).

**2. Set up authentication**

Save the `.env` file to `~/supervisely.env` with your credentials. [Learn about the basics of authentication in Supervisely](https://developer.supervisely.com/getting-started/basics-of-authentication).

The content of this file will look something like this:

```python
SERVER_ADDRESS="https://app.supervise.ly"
API_TOKEN="4r47N.....blablabla......xaTatb"
```

## Upload a Project using CLI

TODO: Change project level to dataset level (upload dataset using CLI)

```bash
supervisely project upload -s <source-local> -id <workspace-id> -n <project-name>
```

In the following **required** arguments, replace:

- `<local-source>` with the local directory where your project is stored. Prefixes: `-s`, `--src`
- `<workspace-id>` with the ID of the target Supervisely workspace. Prefixes: `-id`, `--id`

In the following **optional** arguments, replace:

- `<project-name>` with the name of the project. By default, it takes the name of the source directory. Prefixes: `-n`, `--name`

> Currently available import only in Supervisely format.
> The list of formats currently available to upload using the CLI is not final and may be extended in the future. If you find that a certain format you need is not currently available, you can contact the developers and request that it be added.
