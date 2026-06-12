# Python SDK

### Description

Integrate your workflow with Supervisely or automate processes using Python SDK.

### Overview

To get started, install <a href="https://pypi.org/project/supervisely/" target="_blank">Supervisely Python SDK</a>:

```bash
pip install supervisely
```

An integration example (find more in our <a href="https://developer.supervisely.com/" target="_blank">Developer portal</a>):

```python
# upload mesh
mesh_info = api.mesh.upload_path(<dataset_id>, name="model.ply", path="meshes/model.ply")
# or download mesh
api.mesh.download_path(mesh_info.id, "meshes/model.ply")

# Update project meta
project_meta = sly.ProjectMeta.from_json(api.project.get_meta(<project_id>))
scratch_class = sly.ObjClass("scratch", sly.Mesh, color=[0, 255, 0])
project_meta = project_meta.add_obj_class(scratch_class)
api.project.update_meta(<project_id>, project_meta)

# Create annotation and upload to mesh:
scratch = sly.MeshLabel(sly.Mesh(indices=[0, 1, 2, 3]), scratch_class)
ann = sly.MeshAnnotation(labels=[scratch])
api.mesh.annotation.append(mesh_info.id, ann)
```
