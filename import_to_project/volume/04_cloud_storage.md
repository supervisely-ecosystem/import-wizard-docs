# Cloud Storage

### Description

Import data from connected cloud storage, such as AWS S3, Google Cloud or Azure, with auto-detection of format.

### Overview

✨ _Available in Enterprise Edition._

Import data from connected cloud storage without re-uploading it to Supervisely. Useful for large datasets.

Select folders or files and press `Run`. Supervisely will detect data format, convert, if needed, and import it to Supervisely. Learn how to connect cloud storage [here](https://docs.supervisely.com/enterprise-edition/advanced-tuning/s3).

**Supported providers:** 

`AWS S3`, `GCS (Google Cloud Storage)`, `Azure (Azure Blob Storage)`

**Supported video formats:** 

`.nrrd` `.dcm`

**Annotation formats** (click to see instructions):

- Volumes in any directory structure without annotations (NRRD, DICOM files)
- [Supervisely](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/volumes/supervisely.md)

<br>

**Volume file size limit:**

- Community Free plan: 150MB
- Community Pro plan: 150MB
- Enterprise Edition: Unlimited
