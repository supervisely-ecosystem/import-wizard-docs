<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/export-to-supervisely-format/releases/download/v3.2.6/Icon_blob.png" width="80" style="padding-right: 20px;"> Extended Supervisely Format: Blob </h1>

# Overview

⚠️ **Important:** For most use cases, the standard Supervisely format is sufficient and recommended. This blob format is specifically designed for special cases. Only use this format when dealing with performance bottlenecks related to file system limitations.

Supervisely provides a powerful optimization for projects containing a large number of small image files through its blob file system. Instead of handling thousands of individual files, blob files consolidate many images into a single large binary file. This approach dramatically improves upload and download speeds, especially when dealing with datasets containing tens or hundreds of thousands of images.

Check out the <a href="https://docs.supervisely.com/customization-and-integration/00_ann_format_navi/01_project_structure_new#understanding-blob-files-and-offsets-for-optimized-project-handling" target="_blank">Supervisely JSON format</a> documentation for more details.

🤓 **Annotations remain in the standard Supervisely JSON format** exactly as described below.

The Supervisely json-based annotation format supports such figures: `rectangle`, `line (polyline)`, `polygon`, `point`, `bitmap` (`mask`), `graph` (`keypoints`), `alpha mask`, `2D cuboid`. It is a universal format for various task types and is used in the Supervisely platform. Import as links from cloud storage (with annotations) is supported.

# Format description

**Extended:** ✅ Blob file<br>
**Supported image formats:** `.jpg`, `.jpeg`, `.mpo`, `.bmp`, `.png`, `.webp`, `.tiff`, `.tif`, `.jfif`, `.avif`, `.heic`, and `.heif`<br>
**With annotations:** Yes<br>
**Supported annotation format:** `.json`.<br>
**Data structure:** Information is provided below.

# Input files structure

Example data: [download ⬇️](https://github.com/user-attachments/files/19695484/robots_project_blob.zip).

Both directory and archive are supported.

**Recommended directory structure:**

```text
📂 project-name or 📦 project-name
 ┣ 📂 blob
 ┃  ┗ 📦 small_images.tar
 ┣ 📂 dataset-name-001
 ┃  ┣ 📄 small_images_offsets.pkl
 ┃  ┣ 📂 ann
 ┃  ┃  ┣ 📄 pexels-photo-101063.png.json
 ┃  ┃  ┣ 📄 small-image-0000001.png.json
 ┃  ┃  ┣ ...
 ┃  ┃  ┗ 📄 small-image-0999999.png.json
 ┃  ┗ 📂 img
 ┃     ┗ 🏞️ pexels-photo-101063.png
 ┗ 📄 meta.json
```

Project meta file `meta.json` is recommended to be present in the project directory. It contains classes and tags definitions for the project. If it is not present, app will try to create it from the annotations (if possible). Learn more about the `meta.json` file [here](https://docs.supervisely.com/customization-and-integration/00_ann_format_navi/02_project_classes_and_tags).

## Blob Format Explained

-   A blob file in Supervisely is essentially a `.tar` archive that contains multiple images bundled together.
-   The file naming convention for images inside a blob is the same as for the standard Supervisely format.
-   The offset file `.pkl` is a companion file to the blob archive that contains metadata about where each image is located within the blob file. It's a Python pickle file that maps each image filename to its exact byte position in the blob file.
    For every dataset, you can have multiple blob files, and each file must be described by a separate `.pkl` file containing the offsets of the images that will belong to the dataset.

    ```python

    	# An approximate representation of the content in the pickle file for offsets look like this:

    	[
    		# Batch 1
    		[
    			BlobImageInfo(name='IMG_00001.jpeg', offset_start=0, offset_end=148388),
    			BlobImageInfo(name='IMG_00002.jpeg', offset_start=148388, offset_end=296712),
    			# ...
    		],
    		# Batch 2
    		[
    			BlobImageInfo(name='IMG_10001.jpeg', offset_start=296712, offset_end=445100),
    			BlobImageInfo(name='IMG_10002.jpeg', offset_start=445100, offset_end=593424),
    			# ...
    		],
    		# Batch N
    		# ...
    	]

    	# Offset values are provided as an example.
    ```

-   Projects can also include regular images in the `img` directory of datasets, i.e., they can be mixed.

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

-   `name` - string - image name
-   `description` - string - (optional) - This field is used to store the text we want to assign to the image. In the labeling intrface it corresponds to the 'data' filed.
-   `size` - stores image size. Mostly, it is used to get the image size without the actual image reading to speed up some data processing steps.
-   `width` - image width in pixels
-   `height` - image height in pixels
-   `tags` - **list** of strings that will be interpreted as image <a href="https://docs.supervisely.com/customization-and-integration/00_ann_format_navi/03_supervisely_format_tags" target="_blank">tags</a>
-   `objects` - **list** of <a href="https://docs.supervisely.com/customization-and-integration/00_ann_format_navi/04_supervisely_format_objects" target="_blank">objects on the image</a>

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

-   <a href="https://developer.supervisely.com/getting-started/supervisely-annotation-format" target="_blank">Supervisely Annotation Format</a>
-   <a href="https://developer.supervisely.com/getting-started/supervisely-annotation-format/images" target="_blank">Supervisely Image Annotation</a>
-   <a href="https://developer.supervisely.com/getting-started/command-line-interface/sdk-cli#upload-a-project" target="_blank">[SDK CLI] Upload projects in Supervisely format</a>
-   <a href="https://developer.supervisely.com/getting-started/command-line-interface/cli-tool/workflow-automation#upload-projects-in-supervisely-format" target="_blank">[CLI Tool Beta] Upload projects in Supervisely format</a>
-   <a href="https://ecosystem.supervisely.com/apps/import-images-in-sly-format" target="_blank">[Supervisely Ecosystem] Import images in Supervisely format</a>

    <img data-key="sly-module-link" data-module-slug="supervisely-ecosystem/import-images-in-sly-format" src="https://i.imgur.com/Y6RcQPT.png" width="350px" style='padding-bottom: 10px'/>

-   <a href="https://ecosystem.supervisely.com/apps/export-to-supervisely-format-blob" target="_blank">[Supervisely Ecosystem] Export to Supervisely format: Blob</a>

    <img data-key="sly-module-link" data-module-slug="supervisely-ecosystem/export-to-supervisely-format-blob" src="https://github.com/supervisely-ecosystem/export-to-supervisely-format-blob/releases/download/v0.0.6/app-badge.png" width="420px" style='padding-bottom: 10px'/>
