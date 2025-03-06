<h1 align="left" style="border-bottom: 0"> NIfTI </h1>

# Overview

Easily import your volumes in the NIfTI format.

The converter supports both semantic and instance segmentation annotations, as well as import of unannotated `.nii` files.

**Import from S3 cloud storage is supported.**

The converter is backwards compatible with the <a href="https://ecosystem.supervisely.com/apps/export-volume-project-to-cloud-storage"> Export volume project to cloud storage </a> application. 
If the volumes were originally imported from cloud storage, the **source** volumes will be exported.

All volumes from the input directory and its subdirectories will be uploaded to a single dataset

# Format description

**Supported image formats:** `.nii`.<br>
**With annotations:** Yes<br>
**Supported annotation format:** `.nii`.<br>
**Data structure:** See <a href="#Input-files-structure">Input files structure</a> section.<br>

# Input files structure

The converter supports several input structures:

### Example one: grouped by volume name

The NIfTI file should be structured as follows:
- **volume_name**.nii
- **volume_name**/
    - **cls_name_1**.nii
    - **cls_name_2**.nii
    - ...
- ...

The **volume_name** corresponds to the name of the volume. If the volume has annotations, they should be in the corresponding directory
with the same name as the volume (without extension)

The **cls_name** corresponds to the name of the annotation class. The **cls_name**.nii represents objects of a single class, and should be unique for the current volume (e.g. tumor.nii.gz, lung.nii.gz). `.nii` file can contain multiple objects of the class (each object should be represented by a different value in the mask).

Structure example:

```text
📂 nii
├── 📂 CTChest
│   ├──📦lung.nii.gz
│   └──📦tumor.nii.gz
├──📦CTChest.nii.gz
└──📦Spine.nii.gz
```

### Example two: grouped by plane

The NIfTI file should be structured as follows:
- **prefix**\_anatomic\_**idx**.nii  
- **prefix**\_inference\_**idx**.nii  

The **prefix** should be one of: `cor`, `sag`, `axl`.

The **idx** corresponds to the volume index.

Structure example:

```text
📂nii
├──📄axl_anatomic_1.nii
├──📄axl_inference_1.nii
├──📄cor_anatomic_1.nii
├──📄cor_inference_1.nii
├──📄sag_anatomic_1.nii
└──📄sag_inference_1.nii
```

# Useful links

- <a href="https://ecosystem.supervisely.com/apps/export-volume-project-to-cloud-storage" target="_blank">[Supervisely Ecosystem] Export volume project to cloud storage</a>
