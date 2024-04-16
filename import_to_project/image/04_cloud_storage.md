# Cloud Storage

### Description

Import data from connected cloud storage such as AWS S3, Google Cloud or Azure with auto-detection of annotation format.

### Overview

✨ Available in Enterprise Edition.

Import data from connected cloud storages without re-uploading it to Supervisely. Useful for large datasets.

Select folders or files and press `Run`. Supervisely will automatically detect annotation format, convert, if needed, and import it to Supervisely. Learn how to connect cloud storage [here](https://docs.supervisely.com/enterprise-edition/advanced-tuning/s3).

Select the folder or archive withing containing your data withing your provider and bucket and press the RUN button.
When uploading to an existing project, Supervisely will automatically validate and merge classes, tags, and annotations.

**Supported providers:** `AWS S3` `GCS (Google Cloud Storage)` `Azure (Azure Blob Storage)`

**Supported image formats:** `.jpg` `.jpeg` `.mpo` `.bmp` `.png` `.webp` `.tiff` `.tif` `.nrrd` `.jfif` `.avif` `.heic` `.nii` `.nii.gz` `.dcm`

**Annotation formats (click to see instructions):**

- Images without annotations
- [Supervisely]()
- [COCO]()
- [YOLO]()
- [Pascal VOC]()
- [Cityscapes]()

<details>
  <summary>More formats (click to expand)</summary>

- [Images with masks]()
- [Multi-view images]()
- [Multispectral images]()
- [Medical 2D (single)]()
- [Links from CSV or txt]()
- [PDFs pages as images]()

</details>

<br>

**Single image file size limits:**

- Community Free plan: 25MB
- Community Pro plan: 300MB
- Enterprise Edition: Unlimited
