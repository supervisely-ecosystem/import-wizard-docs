# Cloud Storage

### Description

Import data from connected cloud storage, such as AWS S3, Google Cloud or Azure, with auto-detection of format.

### Overview

✨ _Available in Enterprise Edition._

Import data from connected cloud storages without re-uploading it to Supervisely. Useful for large datasets.

Select folders or files and press `Run`. Supervisely will detect data format, convert, if needed, and import it to Supervisely. Learn how to connect cloud storage [here](https://docs.supervisely.com/enterprise-edition/advanced-tuning/s3).

**Supported providers:**

`AWS S3`, `GCS (Google Cloud Storage)`, `Azure (Azure Blob Storage)`

**Supported point cloud format:**

`.pcd`

**Annotation formats** (click to see instructions):

- PCD Episodes without annotations
- [Supervisely](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/point_cloud_episodes/supervisely.md)

<br>

**Point cloud episodes file size limit:**

- Community Free plan: XX MB
- Community Pro plan: XXX MB
- Enterprise Edition: Unlimited
