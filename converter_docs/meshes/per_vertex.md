# Per-Vertex Annotation

# Overview

This format allows you to import `.ply` mesh files with per-vertex annotations embedded directly in the file. Each vertex carries a `class_id` resolved to a class name via `meta.json`, and a `object_id` to group vertices into object instances.

This is useful when annotations are produced by external pipelines (e.g. 3D segmentation models) that write labels directly into PLY vertex attributes.

# Format description

**Supported mesh formats:** `.ply`<br>
**With annotations:** Yes<br>
**Supported annotation format:** Per-vertex PLY properties + `meta.json`.<br>
**Data structure:** Information is provided below.

# Input files structure

Both directory and archive are supported.

**Recommended directory structure:**

```text
📦 project name
├── 📂 dataset_name
│   ├── 📄 mesh_01.ply
│   └── 📄 mesh_02.ply
└── 📄 meta.json
```

# PLY File Requirements

The `.ply` file must contain the following vertex properties in its header, in addition to the standard geometry properties:

```
property int class_id
property int object_id
```

**Example PLY header:**

```
ply
format ascii 1.0
element vertex 166428
property float x
property float y
property float z
property uchar red
property uchar green
property uchar blue
property uchar alpha
property int class_id
property int object_id
element face 327618
property list uchar int vertex_indices
end_header
```

**Vertex value conventions:**

| Value            | Meaning                                        |
| ---------------- | ---------------------------------------------- |
| `class_id = -1`  | Vertex is not annotated (background)           |
| `object_id = -1` | Vertex does not belong to any object           |
| `class_id > 0`   | Class ID as defined in `meta.json`             |
| `object_id > 0`  | Unique object (instance) ID within the dataset |

# meta.json

The `meta.json` file maps `class_id` integer values to class definitions. It follows the standard Supervisely project meta format with an additional `id` field per class.

**Example `meta.json`:**

```json
{
  "classes": [
    {
      "title": "dot",
      "description": "",
      "shape": "mesh",
      "color": "#000000",
      "geometry_config": {},
      "id": 197748,
      "hotkey": ""
    },
    {
      "title": "scratch",
      "description": "",
      "shape": "any",
      "color": "#6200FF",
      "geometry_config": {},
      "id": 197761,
      "hotkey": ""
    }
  ],
  "tags": [
    {
      "name": "significant",
      "value_type": "none",
      "color": "#FFC705",
      "id": 36942,
      "hotkey": "",
      "applicable_type": "all",
      "classes": [],
      "target_type": "all"
    }
  ],
  "projectType": "meshes"
}
```

The `id` field in each class entry corresponds to the `class_id` value stored per vertex in the `.ply` file.

# How Instances Are Resolved

Vertices sharing the same `object_id` (and the same `class_id`) belong to the same object instance. This allows multiple disconnected regions of the mesh to be grouped into a single labeled object.

**Example:** if three separate mesh patches all have `class_id = 197761` and `object_id = 42`, they will be imported as a single object of class `scratch` with instance ID `42`.

> ⚠️ Each `object_id` must map to exactly one `class_id`.
