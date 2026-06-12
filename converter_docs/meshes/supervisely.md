# Supervisely Format

# Overview

Easiest way to import your meshes with annotations is to use the Supervisely format.
Check out the <a href="https://docs.supervisely.com/data-organization/00_ann_format_navi" target="_blank">Supervisely JSON format</a> documentation for more details.

The Supervisely format for meshes stores labels in a per-mesh `annotation.json` file. Label geometries (vertex index sets) are stored as binary `.bin` files for efficiency, referenced by path from the annotation.

# Format description

**Supported mesh formats:** `.ply`, `.stl`, `.obj`<br>
**With annotations:** Yes<br>
**Supported annotation format:** `.json` + `.bin` geometry files.<br>
**Data structure:** Information is provided below.

# Input files structure

Both directory and archive are supported. Each dataset is a directory with `meshes` and `annotations` subdirectories. Nested datasets are stored in a `datasets` subdirectory of the parent dataset.

**Recommended directory structure:**

```text
📦 project_name
├── 📂 dataset_name
│   ├── 📂 meshes
│   │   ├── 📄 mesh_01.ply
│   │   └── 📄 mesh_02.ply
│   ├── 📂 annotations
│   │   ├── 📂 mesh_01.ply
│   │   │   ├── 📄 annotation.json
│   │   │   └── 📂 geometries
│   │   │       ├── 📄 {label_key}.indices.bin
│   │   │       └── 📄 {label_key}.indices.bin
│   │   └── 📂 mesh_02.ply
│   │       ├── 📄 annotation.json
│   │       └── 📂 geometries
│   │           └── 📄 {label_key}.indices.bin
│   └── 📂 datasets
│       └── 📂 nested_dataset_name
│           ├── 📂 meshes
│           └── 📂 annotations
└── 📄 meta.json
```

Project meta file `meta.json` contains classes and tags definitions. Learn more about the `meta.json` file [here](https://docs.supervisely.com/customization-and-integration/00_ann_format_navi/02_project_classes_and_tags).

# annotation.json

Each mesh has a corresponding `annotation.json` describing its labels.

```json
{
  "key": "b4a3dc33f8d842a79b24942f85f3f2ee",
  "meshId": 6228355,
  "tags": [
    {
      "name": "box_mesh",
      "tagId": 43398,
      "value": 1,
      "id": 1678691
    }
  ],
  "labels": [
    {
      "key": "6e474a08a13f46bcb4c8ca538c760edb",
      "id": 25782697,
      "classTitle": "box",
      "tags": [
        {
          "name": "box_obj",
          "tagId": 43399,
          "value": 1,
          "id": 10171555
        }
      ],
      "geometryType": "mesh",
      "geometry": {
        "indices": null,
        "indicesPath": "geometries/6e474a08a13f46bcb4c8ca538c760edb.indices.bin"
      },
      "priority": 1,
      "customData": {}
    }
  ]
}
```

**Fields definitions:**

- `key` — unique annotation key
- `tags` — entity-level tags of the mesh
- `labels` — list of labeled objects; each label has a `classTitle` and a unique `key`, and stores vertex indices via `indicesPath`
- `indicesPath` — path to the `.bin` file containing the vertex index set for this label (little-endian uint32), relative to the annotation directory of the item
- `meshId`, `id`, `tagId`, `priority`, `customData` and other server-side metadata fields are written on export and are optional on import — they are not required to create the annotations
