<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/import-wizard-docs/assets/48913536/8c27c4ef-9e60-48cc-9797-57872283f9ac" width="80"> Cityscapes Converter </h1>

<br>

This converter allows to import images with `.json` annotations in [Cityscapes](https://github.com/mcordts/cityscapesScripts) format.

⚠️ **Note:** images must have suffix `_leftImg8bit` and annotations suffix `_gtFine_polygons` and `.json` extension.

* **Supported file formats:** all image formats which supported by Supervisely.
* **With annotations:** Yes
* **Grouped by:** No
* **Supported image types:** Not applicable
* **Supported alpha channels:** Not applicable

![cityscapes_result](https://github.com/supervisely-ecosystem/import-wizard-docs/assets/48913536/70b2704b-d986-42e8-88f7-0d150b5cfec0)

# How to use
You can download an example of data for import [here](https://github.com/supervisely-ecosystem/import-wizard-docs/files/14908276/sample_cityscapes.zip).<br>

In order to import custom annotations for the images, you need to provide a `class_to_id.json` file.
This file should contain a list with dictionaries.
Each dictionary should contain information about the class with the following keys:
* `name` - the name of the class. It should be unique.
* `id` - the ID of the class. From 0 to N-1, where N is the number of classes.
* `color` - the color of the class in RGB format. If not specified, the color will be generated randomly

<details>
    <summary>📜class_to_id.json</summary>

```json
[
    {
        "name": "kiwi",
        "id": 1,
        "color": [255, 0, 0]
    },
    {
        "name": "lemon",
        "id": 2,
        "color": [81, 198, 170]
    }
]
```

</details>

Annotation file should contain the following keys:

* `imgHeight` - the height of the image
* `imgWidth` - the width of the image
* `objects` - a list of dictionaries, each containing information about the object
    * `label` - the name of the class
    * `polygon` - a list of points that form the polygon of the object

Example of the annotation file from provided sample data:

<details>
    <summary>📜IMG_1836_gtFine_polygons.json</summary>

```json
{
    "imgHeight": 800,
    "imgWidth": 1067,
    "objects": [
        {
            "label": "lemon",
            "polygon": [
                [772, 421],
                [771, 422],
                ...
                [785, 422],
                [784, 421]
            ]
        },
        {
            "label": "kiwi",
            "polygon": [
                [637, 122],
                [636, 123],
                ...
                [645, 123],
                [644, 122]
            ]
        },
        {
            "label": "kiwi",
            "polygon": [
                [543, 539],
                [542, 540],
                ...
                [548, 540],
                [547, 539]
            ]
        }
    ]
}
```

</details>

Here's an example of the correct directory structure:

```text
📦project name
 ┣ 📂gtFine
 ┃ ┣ 📂test
 ┃ ┃ ┗ 📂ds1
 ┃ ┃ ┃ ┗ 📜IMG_8144_gtFine_polygons.json
 ┃ ┣ 📂train
 ┃ ┃ ┗ 📂ds1
 ┃ ┃ ┃ ┣ 📜IMG_1836_gtFine_polygons.json
 ┃ ┃ ┃ ┣ 📜IMG_2084_gtFine_polygons.json
 ┃ ┃ ┃ ┣ 📜IMG_3861_gtFine_polygons.json
 ┃ ┃ ┃ ┗ 📜IMG_4451_gtFine_polygons.json
 ┃ ┗ 📂val
 ┃ ┃ ┗ 📂ds1
 ┃ ┃ ┃ ┗ 📜IMG_0748_gtFine_polygons.json
 ┣ 📂leftImg8bit
 ┃ ┣ 📂test
 ┃ ┃ ┗ 📂ds1
 ┃ ┃ ┃ ┗ 📜IMG_8144_leftImg8bit.png
 ┃ ┣ 📂train
 ┃ ┃ ┗ 📂ds1
 ┃ ┃ ┃ ┣ 📜IMG_1836_leftImg8bit.png
 ┃ ┃ ┃ ┣ 📜IMG_2084_leftImg8bit.png
 ┃ ┃ ┃ ┣ 📜IMG_3861_leftImg8bit.png
 ┃ ┃ ┃ ┗ 📜IMG_4451_leftImg8bit.png
 ┃ ┗ 📂val
 ┃ ┃ ┗ 📂ds1
 ┃ ┃ ┃ ┗ 📜IMG_0748_leftImg8bit.png
 ┗ 📜class_to_id.json
```

# Useful links
- [Cityscapes format](https://github.com/mcordts/cityscapesScripts)
- [[Supervisely Ecosystem] Import Cityscapes](https://ecosystem.supervisely.com/apps/import-cityscapes)

# Python SDK example

You can also use Supervisely Python SDK to import cityscape format. Here's an example of how to do it:

```python
# TBD after converter release
```
