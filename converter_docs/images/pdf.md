<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/import-wizard-docs/assets/48913536/35d9e8eb-fd4b-4b25-96de-be8d8f191d46" width="80"> PDF Converter </h1>

<br>

# Overview

This converter allows to import `.PDF` files as images in `.PNG` format.
Each page of the `.PDF` file will be converted to a separate image. The images will have a suffix added to their names to indicate the page number.

# Supported file formats

**Supported image formats:** `.pdf`
**With annotations:** Yes<br>
**Supported annotation format:** No<br>
**Grouped by:** Not Applicable<br>

![pdf_result](https://github.com/supervisely-ecosystem/import-wizard-docs/assets/48913536/488fec72-f2fe-4078-a4b3-3105a06e1b8a)

# Input files structure

You can download an example of data for import [here](https://github.com/supervisely-ecosystem/import-wizard-docs/files/14905329/Sample_PDF.zip).<br>

Recommended directory structure:

```text
📦project name
 ┣ 📜Demo_1.pdf
 ┣ 📜Demo_2.pdf
 ┣ 📜Demo_3.pdf
 ┣ 📜Demo_4.pdf
 ┗ 📜Demo_5.pdf
```

# Useful links
- [[Supervisely Ecosystem] Import PDF as Images](https://ecosystem.supervisely.com/apps/import-pdf-as-images)

# Python SDK example

You can also use Supervisely Python SDK to import `.PDF` files. Here's an example of how to do it:

```python
# TBD after converter release
```
