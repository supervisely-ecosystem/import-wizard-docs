<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/import-wizard-docs/assets/48913536/99998ee5-b20c-4104-82af-9a787e863a3b" width="80"> Medical 2D Files Converter </h1>

<br>

# Overview

Medical 2D Converter allows to import 2D files with `.nrrd`, `.dcm`, `.nii` and `.nii.gz` extensions. Files with extensions different from `.nrrd` will be converted to `.nrrd`

**What is DCM file?**<br>

DCM file is an image following Digital Imaging and Communications in Medicine (DICOM) format. Format is used to store various medical images like CT scans, MRIs, PET, ultrasound, etc.

**What is NII file?**<br>

NII format is created by Neuroimaging Informatics Technology Initiative. It is commonly used to store magnetic resonance imaging (MRI) data.

**What is NRRD file?**<br>

NRRD file is a medical imaging format. It is used to store 2D and 3D images along with metadata. It is commonly used in medical imaging.

![medical2d_result]()

# Supported file formats

**Supported image formats:** `.nrrd`, `.dcm`, `.nii` and `.nii.gz`<br>
**With annotations:** No<br>
**Supported annotation format:** Not applicable<br>
**Grouped by:** Not applicable (yet)<br>

# Input files structure

You can download an example of data for import [here]().<br>

Recommended directory structure:

```text
📦project name
 ┣ 📜Image_1.dcm
 ┣ 📜Image_2.dcm
 ┣ 📜Image_3.dcm
 ┣ 📜Image_4.dcm
 ┣ 📜Image_5.DCM
 ┣ 📜Image_6.nrrd
 ┗ 📜Image_7.nii
```

</details>

# Useful links
- [[Supervisely Ecosystem] Import dicom studies](https://ecosystem.supervisely.com/apps/import-dicom-studies)
