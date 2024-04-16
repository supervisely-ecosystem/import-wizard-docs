# Agent Files

### Overview

If you have a large amount of data on your computer that you want to upload, you can connect your machine to Supervisely and symlink or simply copy these data into a specific directory on your computer that is mounted to the agent. They will then appear in Team Files -> Supervisely Agents.
From there, you can select your data, and the auto-import application will upload them to Supervisely.

If you don't have any agent, you can connect your computer with GPU to the platform and use it for model training, inference, and evaluation ✨ for FREE. It is as simple as running a single command in the terminal on your machine. Check out our YouTube tutorials: for [Windows](https://www.youtube.com/watch?v=WR9qrPTn2X8) or [Linux/MacOS](https://www.youtube.com/watch?v=aO7Zc4kTrVg).

Select folder or an archive with data within your agent folder and press the RUN button. Import Wizard will handle the rest: detecting the data format, validating, and uploading to Supervisely.
When uploading to an existing project, Import Wizard will automatically validate and merge classes, tags, and annotations.

**Supported image formats:** `.jpg` `.jpeg` `.mpo` `.bmp` `.png` `.webp` `.tiff` `.tif` `.nrrd` `.jfif` `.avif` `.heic` `.nii` `.nii.gz` `.dcm`

**Annotation formats (click to see instructions):**

- Images without annotations
- [Supervisely]()
- [COCO]()
- [YOLO]()
- [Pascal VOC]()
- [Cityscapes]()

<details>
  <summary>More formats (click to expand)</summary>

- [Images with masks]()
- [Multi-view images]()
- [Multispectral images]()
- [Medical 2D (single)]()
- [Links from CSV or txt]()
- [PDFs pages as images]()

</details>

<br>

**Single image file size limits:**

- Community Free plan: 25MB
- Community Pro plan: 300MB
- Enterprise Edition: Unlimited
