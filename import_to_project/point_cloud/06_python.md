# Python SDK

### Description

Integrate your workflow with Supervisely or automate processes using Python SDK.

### Overview

To get started, install <a href="https://pypi.org/project/supervisely/" target="_blank">Supervisely Python SDK</a>:

```bash
pip install supervisely
```

### Examples

> Find more in our <a href="https://developer.supervisely.com/" target="_blank">Developer portal</a>.

**Upload single point cloud.**

```python
pcd_file = "src/input/pcd/000000.pcd"
pcd_info = api.pointcloud.upload_path(dataset.id, name="pcd_0.pcd", path=pcd_file)
```

**Upload related context image to Supervisely.**

```python
# input files:
img_file = "src/input/img/000000.png"
cam_info_file = "src/input/cam_info/000000.json"

# 0. Read cam_info with matrices (a meta dict).
with open(cam_info_file, "r") as f:
    cam_info = json.load(f)

# 1. Upload an image to the Supervisely. It generates us a hash for image
img_hash = api.pointcloud.upload_related_image(img_file)
# 2. Create img_info needed for matching the image to the point cloud by its ID
img_info = {"entityId": pcd_info.id, "name": "img_0.png", "hash": img_hash, "meta": cam_info}
# 3. Run the API command to attach the image
api.pointcloud.add_related_images([img_info])
```
