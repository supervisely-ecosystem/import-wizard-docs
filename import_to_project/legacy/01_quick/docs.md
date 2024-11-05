# Quick import with the Drag and Drop widget

Intuitive and easy to use, the Drag and Drop widget allows you to upload your local data to the Supervisely platform quickly.

ℹ️ Supported formats are presented below. If no annotation format is detected, the data will be uploaded without annotations.

===== D&D widget =====

### How to use:

1. Drag and drop your data to the widget and wait for the upload to complete.
2. Press the "RUN" button to start the import process.

### Supported data types and formats:

- Images: without annotations or with annotations in [Supervisely](https://docs.supervisely.com/data-organization/00_ann_format_navi), [COCO](https://cocodataset.org/#format-data) (object detection, keypoints, captioning), [YOLO detection](https://docs.ultralytics.com/datasets/detect/), [YOLO segmentation](https://docs.ultralytics.com/datasets/segment/#ultralytics-yolo-format), [Pascal VOC](http://host.robots.ox.ac.uk/pascal/VOC/) formats
- Videos: without annotations or with annotations in [Supervisely](https://docs.supervisely.com/data-organization/00_ann_format_navi), [DAVIS](https://davischallenge.org/index.html), [MOT](https://motchallenge.net/instructions/) formats
- Volumes: without annotations ([DICOM](https://www.dicomstandard.org/current/), [NIfTI](https://nifti.nimh.nih.gov/nifti-1/), [NRRD](https://teem.sourceforge.net/nrrd/format.html)) or with annotations in [Supervisely format](https://docs.supervisely.com/data-organization/00_ann_format_navi)
- Point Clouds: without annotations ([PCD](https://pointclouds.org/documentation/tutorials/pcd_file_format.html), [PLY](http://paulbourke.net/dataformats/ply/), [LAS/LAZ](https://www.asprs.org/wp-content/uploads/2010/12/LAS_1_4_r13.pdf)) or with annotations in [Supervisely format](https://docs.supervisely.com/data-organization/00_ann_format_navi)
- Point Cloud Episodes: without annotations or with annotations in [Supervisely format](https://docs.supervisely.com/data-organization/00_ann_format_navi)
