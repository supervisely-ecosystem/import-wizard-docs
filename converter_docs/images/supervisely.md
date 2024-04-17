<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/import-wizard-docs/releases/download/v0.0.1/sly_logo.png" width="80" style="padding-right: 20px;"> Supervisely Format </h1>

# Overview

Easily import your images with annotations in the Supervisely format. The Supervisely json-based annotation format supports such figures: `rectangle`, `line (polyline)`, `polygon`, `point`, `bitmap` (`mask`), `graph` (`keypoints`). It is a universal format that supports various types of annotations and is used in the Supervisely platform.

> All information about the Supervisely JSON format can be found <a href="https://docs.supervise.ly/data-organization/00_ann_format_navi" target="_blank">here</a>

# Format description

**Supported image formats:** `.jpg`, `.jpeg`, `.mpo`, `.bmp`, `.png`, `.webp`, `.tiff`, `.tif`, and `.jfif`.<br>
**With annotations:** yes<br>
**Supported annotation format:** `.json`.<br>
**Grouped by:** any structure (will be uploaded to a single dataset)<br>

# Input files structure

Example data: [download ⬇️](https://github.com/supervisely-ecosystem/import-images-in-sly-format/files/12537201/robots_project.zip).

Both directory and archive are supported.

**Recommended directory structure:**

```text
  📦input_folder
   ┣ 📂dataset_name_01
   ┃  ┣ 📂ann
   ┃  ┃  ┣ 📄IMG_0748.jpeg.json
   ┃  ┃  ┗ 📄IMG_8144.jpeg.json
   ┃  ┣ 📂img
   ┃  ┃  ┣ 🏞️IMG_0748.jpeg
   ┃  ┃  ┗ 🏞️IMG_8144.jpeg
   ┃  ┗ 📂meta (optional)
   ┃     ┣ 📄IMG_0748.jpeg.json
   ┃     ┗ 📄IMG_8144.jpeg.json
   ┗ 📄meta.json
```

**Struggled with the structure?** No worries!
All images will be uploaded to a single dataset, so you don't have to worry about the full project structure in Supervisely format. All you need is to prepare images with annotations and `meta.json` file (recommended).

Items even can be placed in any subdirectories or the root directory. Just make sure that an annotation file names match the image file names (e.g. annotaions file `image_1.jpg.json` is for the image `image_1.jpg`) and that the annotation file format is correct (we will provide an example in the next section). The application will do the rest.

Project meta file `meta.json` is recommended to be present in the project directory. It contains classes and tags definitions for the project. If it is not present, it will try to create it from the annotations. Learn more about the `meta.json` file <a href="https://docs.supervisely.com/customization-and-integration/00_ann_format_navi/02_project_classes_and_tags" target="_blank">here</a>.

# Individual Image Annotations

For each image, we store the annotations in a separate `json` file named `image_name.image_format.json` with the following file structure:

```json
{
  "description": "food",
  "name": "tomatoes-eggs-dish.jpg",
  "size": {
    "width": 2100,
    "height": 1500
  },
  "tags": [],
  "objects": []
}
```

**Fields definitions:**

- `name` - string - image name
- `description` - string - (optional) - This field is used to store the text we want to assign to the image. In the labeling intrface it corresponds to the 'data' filed.
- `size` - stores image size. Mostly, it is used to get the image size without the actual image reading to speed up some data processing steps.
- `width` - image width in pixels
- `height` - image height in pixels
- `tags` - **list** of strings that will be interpreted as image <a href="https://docs.supervisely.com/customization-and-integration/00_ann_format_navi/03_supervisely_format_tags" target="_blank">tags</a>
- `objects` - **list** of <a href="https://docs.supervisely.com/customization-and-integration/00_ann_format_navi/04_supervisely_format_objects" target="_blank">objects on the image</a>

## Image annotation example with objects and tags

![Image annotation example](https://docs.supervisely.com/~gitbook/image?url=https:%2F%2F1080806899-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F-M4BHwRbuyIoH-xoF3Gv%252Fuploads%252Fgit-blob-552eebcf9ad197da6e9f93912abde5100bd0b196%252Fimage.png%3Falt=media&width=768&dpr=4&quality=100&sign=dec49d5954f46bb85a1ce7ac90dca123b1c3f1e86b35edbea04e012b440d9a29)

Example:

```json
{
  "description": "",
  "tags": [
    {
      "id": 86458971,
      "tagId": 28283797,
      "name": "like",
      "value": null,
      "labelerLogin": "alexxx",
      "createdAt": "2020-08-26T09:12:51.155Z",
      "updatedAt": "2020-08-26T09:12:51.155Z"
    },
    {
      "id": 86458968,
      "tagId": 28283798,
      "name": "situated",
      "value": "outside",
      "labelerLogin": "alexxx",
      "createdAt": "2020-08-26T09:07:26.408Z",
      "updatedAt": "2020-08-26T09:07:26.408Z"
    }
  ],
  "size": {
    "height": 952,
    "width": 1200
  },
  "objects": [
    {
      "id": 497521359,
      "classId": 1661571,
      "description": "",
      "geometryType": "bitmap",
      "labelerLogin": "alexxx",
      "createdAt": "2020-08-07T11:09:51.054Z",
      "updatedAt": "2020-08-07T11:09:51.054Z",
      "tags": [],
      "classTitle": "person",
      "bitmap": {
        "data": "eJwBgQd++IlQTkcNChoKAAAADUlIRF",
        "origin": [535, 66]
      }
    },
    {
      "id": 497521358,
      "classId": 1661574,
      "description": "",
      "geometryType": "rectangle",
      "labelerLogin": "alexxx",
      "createdAt": "2020-08-07T11:09:51.054Z",
      "updatedAt": "2020-08-07T11:09:51.054Z",
      "tags": [],
      "classTitle": "bike",
      "points": {
        "exterior": [
          [0, 236],
          [582, 872]
        ],
        "interior": []
      }
    }
  ]
}
```

# Useful links

- <a href="https://developer.supervisely.com/getting-started/supervisely-annotation-format" target="_blank">Supervisely Annotation Format</a>
- <a href="https://developer.supervisely.com/getting-started/supervisely-annotation-format/images" target="_blank">Supervisely Image Annotation</a>
- <a href="https://developer.supervisely.com/getting-started/command-line-interface/sdk-cli#upload-a-project" target="_blank">[SDK CLI] Upload projects in Supervisely format</a>
- <a href="https://developer.supervisely.com/getting-started/command-line-interface/cli-tool/workflow-automation#upload-projects-in-supervisely-format" target="_blank">[CLI Tool Beta] Upload projects in Supervisely format</a>
- <a href="https://ecosystem.supervisely.com/apps/import-images-in-sly-format" target="_blank">[Supervisely Ecosystem] Import images in Supervisely format</a>

  <img data-key="sly-module-link" data-module-slug="supervisely-ecosystem/import-images-in-sly-format" src="https://i.imgur.com/Y6RcQPT.png" width="350px" style='padding-bottom: 10px'/>
