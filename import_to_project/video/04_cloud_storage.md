# Cloud Storage

### Description

Import data from connected cloud storage such as AWS S3, Google Cloud or Azure with auto-detection of annotation format.

### Overview

✨ Available in Enterprise Edition.

Import data from connected cloud storages without re-uploading it to Supervisely. Useful for large datasets.

Select folders or files and press `Run`. Supervisely will automatically detect annotation format, convert, if needed, and upload it. Learn how to connect cloud storage [here](https://docs.supervisely.com/enterprise-edition/advanced-tuning/s3).

Select the folder or archive withing containing your data withing your provider and bucket and press the RUN button.
When uploading to an existing project, Supervisely will automatically validate and merge classes, tags, and annotations.

**Supported providers:** `S3 (AWS S3)` `GCS (Google Cloud Storage)` `Azure (Azure Blob Storage)`

**Supported video formats:** `.avi` `.mp4` `.3gp` `.flv` `.webm` `.wmv` `.mov` `.mkv`

**Annotation formats (click to see instructions):**

- Videos without annotations
- [Supervisely]()

<br>

**Single video file size limits:**

- Community Free plan: 100MB
- Community Pro plan: 500MB
- Enterprise Edition: Unlimited
