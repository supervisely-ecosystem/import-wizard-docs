# Team Files

> description: Import data from Team Files.

This option allows you to import data from the Team Files. It is a convenient way to import data without uploading it manually every time you want to import the same data.

    === Team Files selector widget ===

### Supported data types and formats:

- Images: without annotations or with annotations in [Supervisely](https://docs.supervise.ly/data-organization/00_ann_format_navi), [COCO](https://cocodataset.org/#format-data) (object detection, keypoints, captioning), [YOLO detection](https://docs.ultralytics.com/datasets/detect/), [YOLO segmentation](https://docs.ultralytics.com/datasets/segment/#ultralytics-yolo-format), [Pascal VOC](http://host.robots.ox.ac.uk/pascal/VOC/) formats
- Videos: without annotations or with annotations in [Supervisely](https://docs.supervise.ly/data-organization/00_ann_format_navi), [DAVIS](https://davischallenge.org/index.html), [MOT](https://motchallenge.net/instructions/) formats
- Volumes: without annotations ([DICOM](https://www.dicomstandard.org/current/), [NIfTI](https://nifti.nimh.nih.gov/nifti-1/), [NRRD](https://teem.sourceforge.net/nrrd/format.html)) or with annotations in [Supervisely format](https://docs.supervise.ly/data-organization/00_ann_format_navi)
- Point Clouds: without annotations ([PCD](https://pointclouds.org/documentation/tutorials/pcd_file_format.html), [PLY](http://paulbourke.net/dataformats/ply/), [LAS/LAZ](https://www.asprs.org/wp-content/uploads/2010/12/LAS_1_4_r13.pdf)) or with annotations in [Supervisely format](https://docs.supervise.ly/data-organization/00_ann_format_navi)
- Point Cloud Episodes: without annotations or with annotations in [Supervisely format](https://docs.supervise.ly/data-organization/00_ann_format_navi)

### How to use

1. Upload your data to the Team Files (if it is not already there).

   ℹ️ The Team Files are the files that are shared with the team. It is located in the `Files` tab of the sidebar.

   ==screenshot: team_files.png==

2. Select the data you want to import from the Team Files.

   ==screenshot: team_files_select.png==

3. Click on the `RUN` button.
