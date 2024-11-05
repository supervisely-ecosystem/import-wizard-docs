[Installation](https://docs.supervisely.com/agents/connect-your-computer)
[How agents work](https://docs.supervisely.com/agents/agent)


# Your Agent

> description: Import data to Supervisely platform using your agent (local machine, server, etc.).

Import data to Supervisely platform using Your Agent. Supports the same data types and formats as the `Quick` import method.

    === Agent files/folders selector widget ===

Suppervisely allows you to connect your own computers with GPU to the platform and use them for model training, inference and evaluation ✨ for FREE.

✅ It is as simple as running a single command in the terminal on your machine. Check out our youtube tutorials: for [Windows](https://www.youtube.com/watch?v=WR9qrPTn2X8) or for [Linux/MacOS](https://www.youtube.com/watch?v=aO7Zc4kTrVg).

And one of features of Your Agent is the ability to run applications on your local machine. You can use it to upload images, videos, volumes, pointclouds, and annotations to Supervisely platform.

### Supported data types and formats:

- Images: without annotations or with annotations in [Supervisely](https://docs.supervisely.com/data-organization/00_ann_format_navi), [COCO](https://cocodataset.org/#format-data) (object detection, keypoints, captioning), [YOLO detection](https://docs.ultralytics.com/datasets/detect/), [YOLO segmentation](https://docs.ultralytics.com/datasets/segment/#ultralytics-yolo-format), [Pascal VOC](http://host.robots.ox.ac.uk/pascal/VOC/) formats
- Videos: without annotations or with annotations in [Supervisely](https://docs.supervisely.com/data-organization/00_ann_format_navi), [DAVIS](https://davischallenge.org/index.html), [MOT](https://motchallenge.net/instructions/) formats
- Volumes: without annotations ([DICOM](https://www.dicomstandard.org/current/), [NIfTI](https://nifti.nimh.nih.gov/nifti-1/), [NRRD](https://teem.sourceforge.net/nrrd/format.html)) or with annotations in [Supervisely format](https://docs.supervisely.com/data-organization/00_ann_format_navi)
- Point Clouds: without annotations ([PCD](https://pointclouds.org/documentation/tutorials/pcd_file_format.html), [PLY](http://paulbourke.net/dataformats/ply/), [LAS/LAZ](https://www.asprs.org/wp-content/uploads/2010/12/LAS_1_4_r13.pdf)) or with annotations in [Supervisely format](https://docs.supervisely.com/data-organization/00_ann_format_navi)
- Point Cloud Episodes: without annotations or with annotations in [Supervisely format](https://docs.supervisely.com/data-organization/00_ann_format_navi)

### How to use

0. Prerequisites: Connect Your Agent (if you haven't done it yet)

   You can find detailed instructions on [how to connect Your Agent](https://docs.supervisely.com/agents/connect-your-computer) (for Windows, Linux, AMI AWS, Kubernetes), [how agent works](https://docs.supervisely.com/agents/agent), and other useful information in the Agents section in the [documentation](https://docs.supervisely.com/)

1. Place your data in the specified folder on your local machine

   ==screenshot: your_agent_folder.png==

2. Select the data (folder) in the widget

   ==screenshot: your_agent_select.png==

3. Press the "RUN" button
