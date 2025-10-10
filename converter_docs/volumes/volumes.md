<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/import-wizard-docs/assets/48913536/fac640ee-a795-4385-b180-c4348dac290a" width="80" style="padding-right: 20px;"> Volumes </h1>

# Overview

This option allows you to upload volumes to the platform without any annotations. All volumes from the input directory and its subdirectories will be uploaded to a single dataset. If you need to preserve the directory structure, you can use the <a href="../../../../supervisely-ecosystem/import-dicom-volumes" target="_blank">Import DICOM Volumes</a> application from the Supervisely Ecosystem.

# Format description

**Supported image formats:** `.nrrd`, `.dcm`.<br>
**With annotations:** No<br>
**Supported annotation format:** Not applicable.<br>
**Grouped by:** Any structure (will be uploaded to a single dataset).<br>

# Input files structure

Example data: [download ⬇️](https://github.com/supervisely-ecosystem/import-wizard-docs/files/15025188/sample_volumes.zip)<br>

Recommended directory structure:

```text
📦folder
┣ 🩻item_01.nrrd
┣ 🩻item_02.nrrd
┣ 🩻item_03.nrrd
┣ 🩻item_04.nrrd
┗ 🩻item_05.nrrd
```

# Useful links

- <a href="../../../../supervisely-ecosystem/import-dicom-volumes" target="_blank">[Supervisely Ecosystem] Import DICOM Volumes</a>
