# Agent Files

### Description

Import data to Sueprvisely from your agent (local machine, server, etc).

### Overview

If you have a large amount of data on your computer that you want to upload, you can connect your machine to Supervisely and symlink or simply copy these data into a specific directory on your computer that is mounted to the agent. They will then appear in Team Files -> Supervisely Agents.
From there, you can select your data, and the auto-import application will upload them to Supervisely.

> If you don't have any agent, you can connect your computer with GPU to the platform and use it for model training, inference, and evaluation ✨ for FREE. It is as simple as running a single command in the terminal on your machine. Check out our YouTube tutorials: for [Windows](https://www.youtube.com/watch?v=WR9qrPTn2X8) or [Linux/MacOS](https://www.youtube.com/watch?v=aO7Zc4kTrVg).

Select folder or an archive with data within your agent folder and press the RUN button. Supervisely will handle the rest: detecting the data format, validating, and uploading to Supervisely.
When uploading to an existing project, Supervisely will automatically validate and merge classes, tags, and annotations.

**Supported image formats:** 

`.jpg` `.jpeg` `.mpo` `.bmp` `.png` `.webp` `.tiff` `.tif` `.nrrd` `.jfif` `.avif` `.heic` `.nii` `.nii.gz` `.dcm`

<details>
  <summary><strong>Annotation formats</strong> (click to expand)</summary>

- Images in any directory structure without annotations
- [Supervisely](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/supervisely.md)
- [COCO](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/coco.md)
- [YOLO](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/yolo.md)
- [Pascal VOC](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/pascal.md)
- [Cityscapes](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/cityscapes.md)
- [Images with masks](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/masks.md)
- [Multi-view images](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/multiview.md)
- [Multispectral images](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/multispectral.md)
- [Medical 2D (single)](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/medical_2d.md)
- [Links from CSV or TXT](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/csv.md)
- [PDFs pages as images](https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/pdf.md)

</details>

<br>

**Image file size limit:**

- Community Free plan: 25MB
- Community Pro plan: 300MB
- Enterprise Edition: Unlimited
