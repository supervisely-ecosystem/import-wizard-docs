# Cloud Storage

### Description

Import data from connected cloud storage such as AWS S3, Google Cloud or Azure with auto-detection of annotation format.

### Overview

✨ Available in Enterprise Edition.

Import data from connected cloud storages without re-uploading it to Supervisely. Useful for large datasets.

Select folders or files and press `Run`. Supervisely will automatically detect annotation format, convert, if needed, and import it to Supervisely. Learn how to connect cloud storage [here](https://docs.supervisely.com/enterprise-edition/advanced-tuning/s3).

Select the folder or archive withing containing your data withing your provider and bucket and press the RUN button.
When uploading to an existing project, Supervisely will automatically validate and merge classes, tags, and annotations.

**Supported providers:** `S3 (AWS S3)` `GCS (Google Cloud Storage)` `Azure (Azure Blob Storage)`

**Supported video formats:** `.nrrd` `.dcm`

**Annotation formats (click to see instructions):**

- Volumes without annotations
- [Supervisely]()

<br>

**Single volume file size limits:**

- Community Free plan: 150MB
- Community Pro plan: 150MB
- Enterprise Edition: Unlimited
