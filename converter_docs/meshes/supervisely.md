# Supervisely Format

# Overview

Easiest way to import your meshes with annotations is to use the Supervisely format.
Check out the <a href="https://docs.supervisely.com/data-organization/00_ann_format_navi" target="_blank">Supervisely JSON format</a> documentation for more details.

The Supervisely format for meshes stores objects in a per-mesh `annotation.json` file. Object geometries (face index sets) are stored as binary `.bin` files for efficiency, referenced by path from the annotation.

# Format description

**Supported mesh formats:** `.ply`, `.stl`, `.obj`<br>
**With annotations:** Yes<br>
**Supported annotation format:** `.json` + `.bin` geometry files.<br>
**Data structure:** Information is provided below.

# Input files structure

Both directory and archive are supported.

**Recommended directory structure:**

```text
📦 project_name
├── 📂 annotations
│   ├── 📂 mesh_01.ply
│   │   ├── 📄 annotation.json
│   │   └── 📂 geometries
│   │       ├── 📄 {object_key}.indices.bin
│   │       └── 📄 {object_key}.indices.bin
│   └── 📂 mesh_02.ply
│       ├── 📄 annotation.json
│       └── 📂 geometries
│           └── 📄 {object_key}.indices.bin
├── 📂 meshes
│   ├── 📄 mesh_01.ply
│   └── 📄 mesh_02.ply
├── 📄 key_id_map.json
└── 📄 meta.json
```

Project meta file `meta.json` contains classes and tags definitions. Learn more about the `meta.json` file [here](https://docs.supervisely.com/customization-and-integration/00_ann_format_navi/02_project_classes_and_tags).

# annotation.json

Each mesh has a corresponding `annotation.json` describing its objects.

```json
{
  "key": "be08c6a07eb04c9c8861c6b85bc97d61",
  "meshId": 6152776,
  "tags": [],
  "objects": [
    {
      "key": "b0a626eac7a741d39c32fc02ac1db32b",
      "id": 417339,
      "classTitle": "tooth",
      "tags": [],
      "geometryType": "mesh",
      "geometry": {
        "indices": null,
        "indicesPath": "geometries/4178a5fbc3284da9876d76ef9688de09.indices.bin"
      }
    }
  ]
}
```

**Fields definitions:**

- `key` — unique annotation key
- `meshId` — ID of the mesh in Supervisely
- `objects` — list of labeled objects; each object has a `classTitle` and a unique `key`, and stores face indices via `indicesPath`
- `indicesPath` — path to the `.bin` file containing the face index set for this object, relative to the annotation folder
