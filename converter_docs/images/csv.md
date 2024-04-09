<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/import-wizard-docs/assets/48913536/34979d8d-6aca-49b0-b3da-7ea38cb21f63" width="80"> CSV, TSV and TXT Converter </h1>

<br>

# Overview

You can easily import Images into Supervisely project using a `.csv`, `.tsv` or `.txt` file. It supports importing images from **Team Files** and by **URLs**. It also allows you to automatically assign tags to each image.

## Key Features
- Import Images from **Team Files**
- Import Images by **URLs** from cloud storage or any accessible internet link
- Supported file formats: `.csv`, `.tsv` or `.txt`
- Automatically **assign Tags** to each Image (_optional_)

## How to Use

All images will be uploaded to a single dataset, so you don't have to worry about the full project structure in Supervisely format. All you need is to prepare a file with URLs or paths and drop this file in quick import.


## Input files structure

In your input file, the first column is crucial as it contains either the paths or URLs to the images you want to import. This column is mandatory for the importer to function correctly.

The second column, which contains the tags, is optional. If provided, these tags will be automatically assigned to the corresponding images upon import. If this column is omitted, the images will be imported without any tags.

Yes, tags are optional for each image. If you choose not to assign tags to certain images, simply leave the tag column blank for those images in your input file. The importer will still process these images and upload them without any tags.

### Delimiters for File Formats

In the context of this importer, we use specific delimiters for different purposes in the `.csv` file:

#### Column Delimiter 
 - `.csv` - A semicolon (`;`) is used to separate different columns. Each column represents a different attribute, such as the image path/url or the image tag.
- `.tsv` - A tab (`\t`) is used as a delimiter to separate different columns. Similar to the `.csv` format, each column represents a different attribute.
- `.txt` - Multiple spaces (` `), tabs (`\t`), or a semicolon (`;`) can be used to separate different columns in a `.txt` file. Each column represents a different attribute, similar to the `.csv` and `.tsv` formats. Please note, ⚠️ a single space (` `) cannot be used as a delimiter.

#### Tag Delimiter

 A comma (`,`) is used to separate different tags assigned to the same image for all file formats. This allows you to assign multiple tags to a single image.

### Examples

Regardless of the file format you choose (`.csv`, `.tsv`, or `.txt`), you can specify either a path or a URL for each image, but not both in the same file. This means that each file should contain either paths to local images or URLs to internet images, but not a mix of both.

1. **Team Files**: Create a `.csv` file with columns for the relative path to the image and the image tag.

    ```csv
        path;tag
        /dogs/img_01.jpeg;dog
        /cats/img_02.jpeg;cat
        /horses/img_01.jpeg;horse
    ```
2. **URLs**: Create a `.txt` file with columns for the full URL-link to the image and the image tag. In this example, tab (`\t`) delimiters are used.

    ```text
        url	tag
        https://images.io/image_example_1.png	tag1,tag2
        https://images.io/image_example_2.png	tag3
        https://images.io/image_example_3.png
    ```

    **Cloud storage link example:**
    <img src="https://user-images.githubusercontent.com/57998637/229191946-d58f8da8-e03e-4e81-bcf2-4c8d804a9843.png" width="1198px">
