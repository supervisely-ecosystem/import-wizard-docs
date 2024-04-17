<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/import-wizard-docs/assets/48913536/4f4ed82c-5567-4aa1-a729-dae5f04ae563" width="80" style="padding-right: 20px;"> Videos </h1>

# Overview

This is the most common format for uploading images to the platform. Supervisely will check and verify the format of the input data and if no other annotation format is detected, the images will be uploaded to the platform.

# Format description

**Supported image formats:** `.avi`, `.mp4`, `.3gp`, `.flv`, `.webm`, `.wmv`, `.mov`, `.mkv`.<br>
**With annotations:** No<br>
**Supported annotation format:** Not applicable.<br>
**Grouped by:** Any structure (uploaded to a single dataset)<br>

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

- <a href="https://ecosystem.supervisely.com/apps/import-videos-supervisely" target="_blank">[Supervisely Ecosystem] Import Videos</a>
