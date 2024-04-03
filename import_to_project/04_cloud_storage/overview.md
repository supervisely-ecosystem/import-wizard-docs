# Cloud Storage

> description: Import data from connected cloud storage to Supervisely platform.

☁️ Cloud storage import allows you to import data from connected cloud storage to Supervisely platform.

It is a convenient way to import data without downloading it to your local machine first. It is especially useful when you have large datasets stored in the cloud.

### Supported providers:

- s3 (AWS S3)
- google (Google Cloud Storage)
- azure (Azure Blob Storage)

### Supported data types and formats:

- Images: without annotations or with annotations in Supervisely, COCO, YOLO, Pascal VOC formats
- Videos: without annotations or with annotations in Supervisely, DAVIS, MOT formats
- Volumes: without annotations (DICOM, NIfTI, NRRD) or with annotations in Supervisely format
- Point Clouds: without annotations (PLY, LAS, LAZ) or with annotations in Supervisely format
- Point Cloud Episodes: without annotations or with annotations in Supervisely format

### How to use:

0. Connect cloud storage to your workspace, if you haven't done it yet.

1. Select the cloud storage you want to import data from.

2. Choose the data you want to import in the selector widget.

3. Click the "RUN" button.
