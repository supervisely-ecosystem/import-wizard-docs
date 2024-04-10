
<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/group-images-for-multiview-labeling/assets/115161827/a9a79a72-59fd-4885-bdd7-eebf3448b49a" width="80" style="padding-right: 20px;"> Multiview Labeling Format</h1>

<br>

# Overview

This import organizes images into groups, adds grouping tags, and activates grouping and multi-tag modes in the project settings. 

# Format description

**Supported format:** structured catalogs<br>
**With annotations:** yes<br>
**Annotation types:** tags <br>
**Grouped by:** tag values<br>

## Key Features
* All images in groups in the created project will be tagged
* `Images Grouping` option will be turned on by default in the created project
* Images will be grouped by tag's value
* Tag value is defined by group directory name
* Works with `.nrrd` image format (2D only)

## How to Use

#### 1. Prepare structure:

  - **Archive** `zip`, `tar`, `tar.xz`, `tar.gz`

    ```text
      📦 my_project.zip
       ┗ 📂 cars catalog
          ┗ 📂 used cars 
             ┣ 📂 105 
             ┃  ┣ 🏞️ car_105_front.jpg
             ┃  ┗ 🏞️ car_105_top.jpg
             ┣ 📂 202 
             ┃  ┣ 🏞️ car_202_front.jpg
             ┃  ┗ 🏞️ car_202_top.jpg
             ┣ 📂 357 
             ┃  ┣ 🏞️ car_357_front.jpg
             ┃  ┗ 🏞️ car_357_top.jpg
             ┣ 🏞️ car_401_front.jpg
             ┣ 🏞️ car_401_top.jpg
             ┗ 🏞️ car_401_side.jpg
    ```

 - **Folder**

    ```text
      📂 cars catalog
       ┗ 📂 used cars
          ┣ 📂 car_id_105
          ┃  ┣ 🏞️ car_105_front.jpg
          ┃  ┗ 🏞️ car_105_top.jpg
          ┣ 📂 car_id_202
          ┃  ┣ 🏞️ car_202_front.jpg
          ┃  ┗ 🏞️ car_202_top.jpg
          ┣ 📂 car_id_357
          ┃  ┣ 🏞️ car_357_front.jpg
          ┃  ┗ 🏞️ car_357_top.jpg
          ┣ 🏞️ car_401_front.jpg
          ┣ 🏞️ car_401_top.jpg
          ┗ 🏞️ car_401_side.jpg
    ```

    #### Structure explained:

    -  Archive must contain only 1 project directory.
    -  Inside project directory must be 1 dataset directory.
    -  Group directories must be populated with images and placed inside dataset directory. All images inside groups will be tagged with folder name value.
    -  All images in the root dataset directory will be uploaded as a regular images and will not be tagged.


    

    **Example Data**: [**IMAGES**](https://github.com/supervisely-ecosystem/import-images-groups/releases/download/v0.0.1/cars.catalog.zip) **|** [**NRRD**](https://github.com/supervisely-ecosystem/import-images-groups/releases/download/v0.0.1/research.zip)

    Example data representation:    
    * **Dataset name:** ds0
    * **Images:**

      |     Image name     |        Tag         |
      | :----------------: | :----------------: |
      | car_105_front.jpg  | `multiview`: `105` |
      | car_105_top.jpg    | `multiview`: `105` |
      | car_202_front.jpg  | `multiview`: `202` |
      | car_202_top.jpg    | `multiview`: `202` |
      | car_357_front.jpg  | `multiview`: `357` |
      | car_357_top.jpg    | `multiview`: `357` |
      | car_401_front.jpg  |
      | car_401_top.jpg    |
      | car_401_side.jpg   |

#### 2. Drop to Import
#### 3. Open imported project using Toolbox 2.0
#### 4. Configure additional Settings after import

 -  To display single images switch off `Images Grouping` setting.

    <img src="https://github.com/supervisely-ecosystem/import-images-groups/releases/download/v0.0.2/enabled-disabled.gif?raw=true"/>

 - If you want to disable images grouping for the whole project, go to `Project` → `Settings` → `Visuals` and uncheck

    <img src="https://i.imgur.com/qOGICD3.png"/>

 -  Windowing tool is available when working with `.nrrd` files. It helps to filter pixels to see bones, air, liquids etc.

    <img src="https://i.imgur.com/gW37Tyn.png"/>

 -  Images view synchronization

    <div>
      <table>
        <tr style="width: 100%">
          <td>
            <b>Synchronization OFF</b>
            <img src="https://user-images.githubusercontent.com/48913536/172838253-4817336b-814b-4504-86cc-870c6665a14b.png" style="width:100%;"/>
          </td>
          <td>
            <b>Synchronization ON</b>
            <img src="https://user-images.githubusercontent.com/48913536/172838244-45fa76cc-50e2-41e5-819a-81ceb3387ade.png" style="width:100%;"/>
          </td>
        </tr>
      </table>
    </div>


# Useful links
- [[Supervisely Ecosystem] Group Images for Multiview Labeling](https://ecosystem.supervisely.com/apps/group-images-for-multiview-labeling)

    <img data-key="sly-module-link" data-module-slug="supervisely-ecosystem/import-images-groups" src="https://github.com/supervisely-ecosystem/group-images-for-multiview-labeling/assets/57998637/823cf901-8d8c-4a64-b884-c59f5ff83e93" width="70%"/>

- [[Supervisely Ecosystem] Import images groups](https://ecosystem.supervisely.com/apps/import-images-groups)

    <img data-key="sly-module-link" data-module-slug="supervisely-ecosystem/import-images-groups" src="https://i.imgur.com/wAiE0ld.png" width="70%"/>
