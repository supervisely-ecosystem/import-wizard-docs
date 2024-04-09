<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/import-wizard-docs/assets/79905215/bd1113e2-b3a5-426a-892f-c747c2eda209" width="80">Pascal format Converter</h1>

<br>

# Overview

The Pascal VOC (Visual Object Classes) format stands as one of the benchmarks established relatively early for object classification, segmentation and detection. It furnishes a standardized dataset for identifying object classes, utilizing an XML-based export format that enjoys widespread adoption in computer vision tasks.
This converter converts Pascal VOC format to Supervisely format. Learn more how to prepare data in Pascal VOC format and how to import the original Pascal VOC dataset in the [Import Pascal VOC](https://ecosystem.supervisely.com/apps/import-pascal-voc) app.

# Supported file formats

**Supported image formats:** `.jpg`, `.jpeg`, `.mpo`, `.bmp`, `.png`, `.webp`, `.tiff`, `.tif`, and `.jfif`.<br>
**With annotations:** yes<br>
**Supported annotation format:** `.xml` (bounding boxes), `.png` (segmentation masks)<br>

# Input files structure

Pascal VOC archive or directory must have the following structure:

```
.
└── custom_pascal.tar                    └── custom_pascal_project_dir
    └── VOCdevkit                            └── VOCdevkit
        └── VOC or VOC2012                       └── VOC or VOC2012
            ├── Annotations                          ├── Annotations
            ├── ImageSets                            ├── ImageSets
            |   ├── Main                             |   ├── Main
            |   └── Segmentation                     |   └── Segmentation
            ├── JPEGImages                           ├── JPEGImages
            ├── SegmentationClass                    ├── SegmentationClass
            ├── SegmentationObject                   ├── SegmentationObject
            └── colors.txt                           └── colors.txt
```

**`colors.txt`** file is custom, and not provided in the original Pascal VOC Dataset. File contains information about instance mask colors associated with classes in Pascal VOC format. This file is required by this app, if you are uploading custom dataset. Each line of `colors.txt` file starts with `class_name` and ends with `RGB` values that represent class color.

**`colors.txt`** example:

```txt
neutral 224 224 192
kiwi 255 0 0
lemon 81 198 170
```

**Action and Layout Classification Image Sets are not supported by import application.**