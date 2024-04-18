# Python SDK

### Description

Integrate your workflow with Supervisely or automate processes using Python SDK.

### Overview

To get started, install <a href="https://pypi.org/project/supervisely/" target="_blank">Supervisely Python SDK</a>:

```bash
pip install supervisely
```

### Examples

For more information, visit our <a href="https://developer.supervisely.com/" target="_blank">Developer Portal</a>.

**Upload one point cloud to Supervisely.**

```python
meta = {"frame": 0}  # "frame" is a required field for Episodes
pcd_info = api.pointcloud_episode.upload_path(dataset.id, "pcd_0.pcd", "src/input/pcd/000000.pcd", meta=meta)
```

**Upload entire point clouds episode to Supervisely platform.**

```python
def read_cam_info(cam_info_file):
    with open(cam_info_file, "r") as f:
        cam_info = json.load(f)
    return cam_info


# 1. get paths
input_path = "src/input"
pcd_files = list(Path(f"{input_path}/pcd").glob("*.pcd"))
img_files = list(Path(f"{input_path}/img").glob("*.png"))
cam_info_files = Path(f"{input_path}/cam_info").glob("*.json")

# 2. get names and metas
pcd_metas = [{"frame": i} for i in range(len(pcd_files))]
img_metas = [read_cam_info(cam_info_file) for cam_info_file in cam_info_files]
pcd_names = list(map(os.path.basename, pcd_files))
img_names = list(map(os.path.basename, img_files))

# 3. upload
pcd_infos = api.pointcloud_episode.upload_paths(dataset.id, pcd_names, pcd_files, metas=pcd_metas)
img_hashes = api.pointcloud.upload_related_images(img_files)
img_infos = [
    {"entityId": pcd_infos[i].id, "name": img_names[i], "hash": img_hashes[i], "meta": img_metas[i]}
    for i in range(len(img_hashes))
]
api.pointcloud.add_related_images(img_infos)
```
