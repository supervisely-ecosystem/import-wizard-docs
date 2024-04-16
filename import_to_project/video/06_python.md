# Python SDK

### Description

Integrate your workflow with Supervisely or automate processes using Python SDK.

### Overview

To get started, install Supervisely Python SDK:

```bash
pip install supervisely
```

An integration example:

```python
# upload video
video_info = api.video.upload_path(<dataset_id>, name="my-cats.mp4", path="videos/my-cats.mp4")
# or download video
api.video.download_path(video_info.id, save_path)

# Update project meta
project_meta = sly.ProjectMeta.from_json(api.project.get_meta(<project_id>)
kiwi_obj_cls = sly.ObjClass("kiwi", sly.Rectangle, color=[0, 0, 255])
project_meta = project_meta.add_obj_class(kiwi_obj_cls)
api.project.update_meta(<project_id>, project_meta)

# Create annotation:
points = [
    [136, 632, 350, 817],
    [139, 655, 355, 842],
    [145, 672, 361, 864],
]
kiwi = sly.VideoObject(kiwi_obj_cls)
frames = []
for i, coords in enumerate(points):
    bbox = sly.Rectangle(*points[fr_index])
    bbox_figure = sly.VideoFigure(kiwi, bbox, i)
    frame = sly.Frame(i, figures=[bbox_figure])
    frames.append(frame)
objects = sly.VideoObjectCollection([kiwi, orange])
frames = sly.FrameCollection(frames)
frame_size, vlength = sly.video.get_image_size_and_frames_count(video_path)

video_ann = sly.VideoAnnotation(
    img_size=frame_size,
    frames_count=vlength,
    objects=objects,
    frames=frames,
)

# upload annotation to server
api.video.annotation.append(video_info.id, video_ann)

# download annotation from server
video_ann_json = api.video.annotation.download(video_info.id) # JSON
key_id_map = sly.KeyIdMap()
video_ann = sly.VideoAnnotation.from_json(video_ann_json, project_meta, key_id_map)
```
