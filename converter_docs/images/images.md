<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/import-wizard-docs/assets/48913536/d3dd2142-7b22-4968-9d28-69a62c76e7c3" width="80" style="padding-right: 20px;"> Images </h1>

# Overview

This option allows you to upload images to the platform without any annotations. All images from the input directory and its subdirectories will be uploaded to a single dataset. If you need to preserve the directory structure, you can use the <a href="https://ecosystem.supervisely.com/apps/import-images" target="_blank">Import Images</a> application from the Supervisely Ecosystem.

# Format description

**Supported image formats:** `.jpg`, `.jpeg`, `.mpo`, `.bmp`, `.png`, `.webp`, `.tiff`, `.tif`, `.jfif`, `.avif`, `.heic`, and `.heif`<br>
**With annotations:** No<br>
**Supported annotation format:** Not applicable.<br>
**Grouped by:** Any structure (will be uploaded as a single dataset).<br>

# Input files structure

Example data: [download ⬇️](https://github.com/supervisely-ecosystem/import-wizard-docs/files/15013758/sample_images.zip)<br>

Recommended directory structure:

```text
📦project name
┣ 🖼️IMG_01.png
┣ 🖼️IMG_02.png
┣ 🖼️IMG_03.png
┣ 🖼️IMG_04.png
┣ 🖼️IMG_05.png
┣ 🖼️IMG_06.png
┣ 🖼️IMG_07.png
┣ 🖼️IMG_08.png
┣ 🖼️IMG_09.png
┗ 🖼️IMG_10.png
```

# Useful links

- <a href="https://ecosystem.supervisely.com/apps/import-images" target="_blank">[Supervisely Ecosystem] Import Images</a>
