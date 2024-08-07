<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/import-wizard-docs/releases/download/v0.0.1/multispectral_logo.png" width="80" style="padding-right: 20px;"> Multispectral Images Format </h1>

# Overview

This converter allows to import of multispectral images as channels or as separate images without annotations.<br>
Images will be grouped by directories, files from the "split" directory will be split into separate images by channels and the files from the "images" directory will be uploaded as they are.<br>

> Note: To use the multispectral import feature, you need to create a project with the `Multispectral image annotation` setting enabled. You can also enable this setting in the project settings after the import. Here is a illustration of how to upload multispectral images:

![Import Multispectral images](https://github.com/supervisely-ecosystem/import-wizard-docs/assets/79905215/5571a96b-9c2f-42cd-abed-904acec3d625)

Result of the import:

![Result of the import](https://developer.supervisely.com/~gitbook/image?url=https:%2F%2Fgithub-production-user-asset-6210df.s3.amazonaws.com%2F118521851%2F286217532-c6551cd6-d207-4d13-a9ce-9b31d3e57b8f.png&width=768&dpr=2&quality=100&sign=5575e36422d48d1b5023237e4dd251079e05d8bb2227741e4fc119501625c1b5)

# Format description

**Supported image formats:** `.jpg`, `.jpeg`, `.mpo`, `.bmp`, `.png`, `.webp`, `.tiff`, `.tif`, `.jfif`, `.avif`, `.heic`, and `.heif`<br>
**With annotations:** No<br>
**Supported annotation format:** Not applicable <br>
**Grouped by:** Folders (corresponding tags will be assigned to images)<br>

# Input files structure

Example data: [download ⬇️](https://github.com/supervisely-ecosystem/import-multispectral-images/files/13487269/demo_data.zip)<br>

Recommended directory structure:

```text
  📦project_name
   ┣ 📂group_name_1
   ┃  ┗ 📂split
   ┃     ┗ 🏞️demo1.png
   ┣ 📂group_name_2
   ┃  ┣ 📂images
   ┃  ┃  ┣ 🏞️demo4-rgb.png
   ┃  ┃  ┗ 🏞️demo4-thermal.png
   ┃  ┗ 📂split
   ┃     ┗ 🏞️demo4-thermal copy.png
   ┗ 📂group_name_3
      ┗ 📂images
         ┣ 🏞️demo8-mri1.png
         ┣ 🏞️demo8-mri2.png
         ┗ 🏞️demo8-rgb.png
```

In this example, we have 3 groups with images. In the first group, we have one image, which should be split. In the second group, we have one image, which should be split and two images, which should be uploaded as is. In the third group, we have three images, which should be uploaded as is.<br>

# Useful links

- [[Supervisely Developer Portal] Multispectral Images](https://developer.supervisely.com/getting-started/python-sdk-tutorials/images/multispectral-images)
- [[Supervisely Blog] How to Annotate Multispectral Images for Computer Vision Models](https://supervisely.com/blog/labeling-multispectral-images/)
- [[Supervisely Ecosystem] Import Multispectral Images](https://ecosystem.supervisely.com/apps/import-multispectral-images)

# Python SDK example

You can also use Supervisely Python SDK to import multispectral images. Here's an example of how to do it:

```python
# Import required libraries.
import cv2
import os
import supervisely as sly
from dotenv import load_dotenv

# Paste your team_id and workspace_id here.
team_id = 448
workspace_id = 690

# Load .env file with your API token and the server address.
load_dotenv(os.path.expanduser("~/supervisely.env"))

# Initialize the API.
api = sly.Api.from_env()

# Create a new project and dataset.
project = api.project.create(workspace_id, "Multispectral images", change_name_if_conflict=True)
dataset = api.dataset.create(project.id, "ds0")

# Set the multispectral settings for the project.
api.project.set_multispectral_settings(project.id)

# Upload RGB image, thermal image, and channels of thermal image.
image_name = "demo7.png"
images = ["demo_data/demo7-rgb.png", "demo_data/demo7-thermal.png"]

image = cv2.imread(images[1])

# Extract channels as 2d numpy arrays: channels = [a, b, c]
channels = [image[:, :, i] for i in range(image.shape[2])]

image_infos = api.image.upload_multispectral(dataset.id, image_name, channels, images)
```

This code will create a new project and dataset, set the multispectral settings for the project, and upload the RGB image, thermal image, and channels of the thermal image into one group.<br>
