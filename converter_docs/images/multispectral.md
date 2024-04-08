# Overview

This converter allows to import of multispectral images as channels or as separate images without annotations.<br>
Images will be grouped by directories, files from the "split" directory will be split into separate images by channels and the files from the "images" directory will be uploaded as they are.<br>

# Supported file formats
All image formats which supported by Supervisely. | Добавить ссылку?

# Results?
Сделать минималистичную инфографику что это картинки, что нет аннотаций, что они сгруппированы? Какие типо изображений поддерживаются (ну там типо 8 битные, альфа каналы и проч)? Совместить этот раздел с предыдущим? Или вообще это все в Overview?<br>

**Supported file formats:** all image formats which supported by Supervisely.<br>
**With annotations:** no<br>
**Grouped by:** directories<br>
**Supported image types:** 8-bit<br>
**Supported alpha channels:** yes<br>


![Result of the import](https://developer.supervisely.com/~gitbook/image?url=https:%2F%2Fgithub-production-user-asset-6210df.s3.amazonaws.com%2F118521851%2F286217532-c6551cd6-d207-4d13-a9ce-9b31d3e57b8f.png&width=768&dpr=2&quality=100&sign=5575e36422d48d1b5023237e4dd251079e05d8bb2227741e4fc119501625c1b5)

# How to use

You can download an example of data for import [here](https://github.com/supervisely-ecosystem/import-multispectral-images/files/13487269/demo_data.zip).<br>
Here's an example of the correct directory structure:

```text
📦 project_name
 ┣ 📂 group_name_1
 ┃ ┣ 📂 split
 ┃ ┃ ┗ 🏞️ demo1.png
 ┣ 📂 group_name_2
 ┃ ┣ 📂 images
 ┃ ┃ ┣ 🏞️ demo4-rgb.png
 ┃ ┃ ┗ 🏞️ demo4-thermal.png
 ┃ ┣ 📂 split
 ┃ ┃ ┗ 🏞️ demo4-thermal copy.png
 ┣ 📂 group_name_3
 ┃ ┣ 📂 images
 ┃ ┃ ┣ 🏞️ demo8-mri1.png
 ┃ ┃ ┣ 🏞️ demo8-mri2.png
 ┃ ┃ ┗ 🏞️ demo8-rgb.png
```

In this example, we have 3 groups with images. In the first group, we have one image, which should be split. In the second group, we have one image, which should be split and two images, which should be uploaded as is. In the third group, we have three images, which should be uploaded as is.<br>

# Useful links
- [[Supervisely Developer Portal] Multispectral Images](https://developer.supervisely.com/getting-started/python-sdk-tutorials/images/multispectral-images)
- [[Supervisely Blog] How to Annotate Multispectral Images for Computer Vision Models](https://supervisely.com/blog/labeling-multispectral-images/)
- [[Supervisely Ecosystem] Import Multispectral Images](https://ecosystem.supervisely.com/apps/import-multispectral-images)