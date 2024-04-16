# Cloud Storage

### Description

Import data from connected cloud storage, such as AWS S3, Google Cloud or Azure, with auto-detection of format.

### Overview

✨ _Available in Enterprise Edition._

Import data from connected cloud storage without re-uploading it to Supervisely. Useful for large datasets.

Select folders or files and press `Run`. Supervisely will detect data format, convert, if needed, and import it to Supervisely. Learn how to connect cloud storage [here](https://docs.supervisely.com/enterprise-edition/advanced-tuning/s3).

**Supported providers:** 

`AWS S3`, `GCS (Google Cloud Storage)`, `Azure (Azure Blob Storage)`

**Supported image formats:** 

`.jpg` `.jpeg` `.mpo` `.bmp` `.png` `.webp` `.tiff` `.tif` `.nrrd` `.jfif` `.avif` `.heic` `.nii` `.nii.gz` `.dcm`

**Annotation formats** (click to see instructions):

- Images in any directory structure without annotations
- [Supervisely](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/supervisely.md)
- [COCO](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/coco.md)
- [YOLO](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/yolo.md)
- [Pascal VOC](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/pascal.md)
- [Cityscapes](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/cityscapes.md)

<details>
  <summary>More formats (click to expand)</summary>

- [Images with masks](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/masks.md)
- [Multi-view images](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/multiview.md)
- [Multispectral images](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/multispectral.md)
- [Medical 2D (single)](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/medical_2d.md)
- [Links from CSV or TXT](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/csv.md)
- [PDFs pages as images](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/pdf.md)

</details>

<br>
