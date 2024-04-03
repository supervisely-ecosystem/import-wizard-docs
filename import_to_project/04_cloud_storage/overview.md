# Cloud Storage

> description: Import data from connected cloud storage to Supervisely platform.

☁️ Cloud storage import allows you to import data from cloud storage connected to Supervisely platform.

It is a convenient way to import data without downloading it to your local machine first. It is especially useful when you have large datasets stored in the cloud.

### Supported providers:

- s3 (AWS S3)
- google (Google Cloud Storage)
- azure (Azure Blob Storage)

### Supported data types and formats:

- Images: without annotations or with annotations in [Supervisely](https://docs.supervise.ly/data-organization/00_ann_format_navi), [COCO](https://cocodataset.org/#format-data) (object detection, keypoints, captioning), [YOLO detection](https://docs.ultralytics.com/datasets/detect/), [YOLO segmentation](https://docs.ultralytics.com/datasets/segment/#ultralytics-yolo-format), Pascal VOC formats
- Videos: without annotations or with annotations in [Supervisely](https://docs.supervise.ly/data-organization/00_ann_format_navi), [DAVIS](https://davischallenge.org/index.html), [MOT](https://motchallenge.net/instructions/) formats
- Volumes: without annotations ([DICOM](https://www.dicomstandard.org/current/), [NIfTI](https://nifti.nimh.nih.gov/nifti-1/), [NRRD](https://teem.sourceforge.net/nrrd/format.html)) or with annotations in [Supervisely format](https://docs.supervise.ly/data-organization/00_ann_format_navi)
- Point Clouds: without annotations ([PCD](https://pointclouds.org/documentation/tutorials/pcd_file_format.html), [PLY](http://paulbourke.net/dataformats/ply/), [LAS/LAZ](https://www.asprs.org/wp-content/uploads/2010/12/LAS_1_4_r13.pdf)) or with annotations in [Supervisely format](https://docs.supervise.ly/data-organization/00_ann_format_navi)
- Point Cloud Episodes: without annotations or with annotations in [Supervisely format](https://docs.supervise.ly/data-organization/00_ann_format_navi)


### How to use:

0. Connect cloud storage to your workspace, if you haven't done it yet.

1. Select the cloud storage you want to import data from.

2. Choose the data you want to import in the selector widget.

3. Click the "RUN" button.
