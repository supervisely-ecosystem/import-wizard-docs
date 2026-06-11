# Per-Vertex Annotation

# Overview

This format allows you to import `.ply` mesh files with per-vertex annotations embedded directly in the file. Each annotated vertex is painted with the color of its class (vertex colors are matched against class colors from `meta.json`), and an `object_id` groups vertices into object instances.

This is useful when annotations are produced by external pipelines (e.g. 3D segmentation models) that write labels directly into PLY vertex attributes.

# Format description

**Supported mesh formats:** `.ply` (ASCII only)<br>
**With annotations:** Yes<br>
**Supported annotation format:** Per-vertex PLY properties + `meta.json`.<br>
**Data structure:** Information is provided below.

# Input files structure

Both directory and archive are supported. Datasets may be nested; the directory hierarchy is preserved as a nested dataset hierarchy. Mesh files placed directly next to `meta.json` are imported into a default dataset.

**Recommended directory structure:**

```text
📦 project name
├── 📂 dataset_name
│   ├── 📄 mesh_01.ply
│   ├── 📄 mesh_02.ply
│   └── 📂 nested_dataset_name
│       └── 📄 mesh_03.ply
└── 📄 meta.json
```

# PLY File Requirements

The `.ply` file must be in **ASCII** format (`format ascii 1.0`; binary PLY is not supported) and must contain per-vertex color properties (`red`, `green`, `blue` or `diffuse_red`, `diffuse_green`, `diffuse_blue`) in addition to the standard geometry properties:

```
property uchar red
property uchar green
property uchar blue
property int class_id
property int object_id
```

- **Vertex colors** define the annotation: a vertex whose color exactly matches the color of a class from `meta.json` is imported as annotated with that class. Any other color (including white, the recommended neutral color for unannotated vertices) means the vertex is not annotated.
- **`object_id`** is needed to reconstruct object instances: vertices sharing the same `object_id` are grouped into a single object. Without it, all vertices of a class are merged into one object.
- **`class_id`** is not used during import (classes are resolved by color); it is written on export for convenience of downstream PLY processing.

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

| Value                       | Meaning                                         |
| --------------------------- | ----------------------------------------------- |
| color matches a class color | Vertex is annotated with that class             |
| any other color             | Vertex is not annotated (background)            |
| `object_id = -1`            | Vertex does not belong to any object instance   |
| `object_id >= 0`            | Unique object (instance) ID within the mesh     |
| `class_id = -1`             | Auxiliary marker: vertex is not annotated       |
| `class_id > 0`              | Auxiliary: class ID, written for downstream use |

> ℹ️ White (`255 255 255`) is reserved as the neutral color for unannotated vertices — do not use it as a class color.

# meta.json

The `meta.json` file defines the classes. Vertex colors in the `.ply` files are matched against the `color` field of each class, so **class colors must be unique**. Classes must have shape `mesh` or `any`, and `projectType` must be `meshes`. The file follows the standard Supervisely project meta format.

**Example `meta.json`:**

```json
{
  "classes": [
    {
      "title": "dot",
      "description": "",
      "shape": "mesh",
      "color": "#FF0000",
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

At least one mesh in the project must contain annotated vertices (colors matching a class), otherwise the format will not be detected.

# How Instances Are Resolved

Vertices sharing the same `object_id` (and the same class color) belong to the same object instance. This allows multiple disconnected regions of the mesh to be grouped into a single labeled object.

**Example:** if three separate mesh patches all have the color of class `scratch` and `object_id = 42`, they will be imported as a single object of class `scratch` with instance ID `42`.

> ⚠️ Each `object_id` must map to exactly one class.

# Mesh Cleanup on Import

The label data baked into the `.ply` files is used only to build the annotations. The mesh files stored on the platform are cleaned up during import: `class_id`/`object_id` properties are removed, and label paint is reset (annotated vertices are repainted with neutral white; if every vertex was annotated, the color properties are removed entirely). Original, non-label vertex colors are preserved.
