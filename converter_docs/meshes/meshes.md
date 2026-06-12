# Meshes

# Overview

This option allows you to upload mesh files to the platform without any annotations. All meshes from the input directory and its subdirectories will be uploaded to a single dataset.

# Format description

**Supported mesh formats:** `.ply`, `.stl`, `.obj`<br>
**With annotations:** No<br>
**Supported annotation format:** Not applicable.<br>
**Grouped by:** Any structure (will be uploaded as a single dataset).<br>

# Input files structure

Recommended directory structure:

```text
📦 project name
├── 📄 mesh_01.ply
├── 📄 mesh_02.stl
├── 📄 mesh_03.obj
└── 📄 mesh_04.ply
```
