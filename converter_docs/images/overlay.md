<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/import-wizard-docs/releases/download/v0.0.1/sly_logo.png" width="80" style="padding-right: 20px;"> Overlay Images </h1>

# Overview

This format allows you to upload source images together with one or multiple overlay images for each source image.

Image annotations are also supported, but only for source images. Overlay images are treated as additional visual layers and do not have separate annotation files.

The format follows a Supervisely-like dataset structure, where source images are stored in the `img` directory and overlays are stored separately in the `overlay` directory.

# Format description

**Supported base image formats:** `.jpg`, `.jpeg`, `.mpo`, `.bmp`, `.png`, `.webp`, `.tiff`, `.tif`, `.jfif`, `.avif`, `.heic`, and `.heif`<br>
**Supported overlay image formats:** `.jpg`, `.jpeg`, `.bmp`, `.png`, `.webp`, `.tiff`, `.tif`, `.avif`, `.heic`, and `.heif` (`.png` is recommended when transparency is needed)<br>
**With annotations:** Yes, for source images only<br>
**With overlays:** Yes<br>
**Supported annotation format:** `.json` for source image annotations<br>
**Data structure:** Information is provided below.<br>

# Input files structure

Both directory and archive are supported.

**Recommended directory structure:**

```text
📦input_folder
┣ 📂dataset_name_01
┃  ┣ 📂ann
┃  ┃  ┣ 📄image_001.jpg.json
┃  ┃  ┗ 📄image_002.jpg.json
┃  ┣ 📂img
┃  ┃  ┣ 🖼️image_001.jpg
┃  ┃  ┗ 🖼️image_002.jpg
┃  ┗ 📂overlay
┃     ┣ 📂image_001.jpg
┃     ┃  ┣ 🖼️overlay_01.png
┃     ┃  ┗ 🖼️overlay_02.png
┃     ┗ 📂image_002.jpg
┃        ┗ 🖼️overlay.png
┗ 📂dataset_name_02
	 ┣ 📂ann
	 ┃  ┗ 📄frame_001.png.json
	 ┣ 📂img
	 ┃  ┗ 🖼️frame_001.png
	 ┗ 📂overlay
			┗ 📂frame_001.png
				 ┗ 🖼️heatmap.png
```

## Structure rules

- Source images must be placed in the `img` directory.
- Source image annotations must be placed in the `ann` directory and follow the standard Supervisely naming rule: `image_name.ext.json`.
- Overlay images must be placed in the `overlay` directory.
- Inside `overlay`, each subdirectory must be named exactly as the corresponding source image file, including extension.
  - Example: `img/image_001.jpg` → `overlay/image_001.jpg/`
- Each image subdirectory inside `overlay` may contain one or multiple overlay images.
- Overlay images are matched to the source image by the name of the subdirectory, not by overlay file name.
- Annotation files are matched only to source images.
- Overlay display settings such as opacity are configured in the web interface and are not expected in the file system.

## Recommendations

- It is recommended that each overlay image has the same width and height as the source image.
- Use `.png` overlays when you need transparency.
- If only one overlay is provided for an image, it should still be placed inside that image's overlay subdirectory.

## Example mapping

- `img/image_001.jpg`
  - `ann/image_001.jpg.json`
  - `overlay/image_001.jpg/overlay_01.png`
  - `overlay/image_001.jpg/overlay_02.png`
- `img/image_002.jpg`
  - `ann/image_002.jpg.json`
  - `overlay/image_002.jpg/overlay.png`

In this example, `image_001.jpg` will have a standard Supervisely annotation file and two overlays, while `image_002.jpg` will have one annotation file and one overlay.

## Source image annotations

Annotation files for source images use the standard Supervisely image annotation format. For each source image, the annotation file must be stored in `ann` and named as `image_name.ext.json`.

Example:

- `img/image_001.jpg`
- `ann/image_001.jpg.json`

Overlay images do not require annotation files.

# Useful links

- <a href="https://ecosystem.supervisely.com/apps/import-images" target="_blank">[Supervisely Ecosystem] Import Images</a>
- <a href="https://developer.supervisely.com/getting-started/supervisely-annotation-format/images" target="_blank">Supervisely Image Annotation</a>
