<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/import-wizard-docs/releases/download/v0.0.1/medical2d_logo.png" width="80"> Medical 2D Files Converter </h1>

# Overview

Medical 2D Converter allows to import 2D files with `.nrrd`, `.dcm`, `.nii` and `.nii.gz` extensions. Files with extensions different from `.nrrd` will be converted to `.nrrd`

While this converter primarily supports 2D medical images, it is possible to import 3D files. However, please note that 3D files will be transposed and sliced along the axial plane. This process converts the 3D image into a series of 2D slices, which can then be viewed and analyzed individually.

# Format description

**Supported image formats:** `.nrrd`, `.dcm`, `.nii` and `.nii.gz`<br>
**With annotations:** No<br>
**Grouped by:** Any structure (will be uploaded as a single dataset)<br>

## Formats explained

- **DCM**

  `DCM` file is an image following Digital Imaging and Communications in Medicine (DICOM) format. Format is used to store various medical images like CT scans, MRIs, PET, ultrasound, etc.

  Uses `.dcm` and `.DICOM` extensions

  If your DICOM data contains one of the following metadata fields, it will be used as `group` tag in the project:

    - `StudyInstanceUID`
    - `StudyID`
    - `SeriesInstanceUID`
    - `TreatmentSessionUID`
    - `Manufacturer`
    - `ManufacturerModelName`
    - `Modality`

  Moreover, all other DICOM metadata will be saved as image metadata and can be viewed in the Labeling interface.

  ***

- **NRRD**

  `NRRD` file is a medical imaging format. It is used to store 2D and 3D images along with metadata. It is commonly used in medical imaging.

  Uses `.nrrd` extension.

  ***

- **NII**

  `NII` format is commonly used to store magnetic resonance imaging (MRI) data.

  Uses `.nii` and `.nii.gz` extensions.

![Medical data import results](https://github.com/supervisely-ecosystem/import-wizard-docs/assets/48913536/b56c3c90-05ef-4932-a5d2-7b3714a43d1d)

# Input files structure

Example data: [download ⬇️](https://github.com/supervisely-ecosystem/import-wizard-docs/files/14934438/sample_medical2d.zip)<br>

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

# Useful links

- <a href="https://ecosystem.supervisely.com/apps/import-dicom-studies" target="_blank">[Supervisely Ecosystem] Import DICOM studies</a>
- <a href="https://teem.sourceforge.net/nrrd/" target="_blank">Nearly Raw Raster Data (NRRD): Format, Examples etc.</a>
- <a href="https://dicom.nema.org/medical/dicom/current/output/html/part01.html#chapter_6" target="_blank">Overview of The Content of The DICOM Standard</a>
- <a href="https://nifti.nimh.nih.gov/" target="_blank">Neuroimaging Informatics Technology Initiative (NIfTI)</a>
