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
# upload image
image_info = api.image.upload_path(<dataset_id>, name="my-cats.jpg", path="images/my-cats.jpg")
# or download image
img = api.image.download_np(image_info.id)  # RGB ndarray

# Update project meta
project_meta = sly.ProjectMeta.from_json(api.project.get_meta(<project_id>)
cat_class = sly.ObjClass("cat", sly.Rectangle, color=[0, 255, 0])
project_meta = project_meta.add_obj_class(cat_class)
api.project.update_meta(<project_id>, project_meta)

# Create annotation and upload to image:
cat = sly.Label(sly.Rectangle(top=100, left=150, bottom=200, right=250), cat_class)
ann = sly.Annotation(img_size=[img.height, img.width], labels=[cat])
api.annotation.upload_ann(image_info.id, ann)
```

To learn more about Supervisely Python SDK click <a href="https://developer.supervisely.com/" target="_blank">here</a>.
