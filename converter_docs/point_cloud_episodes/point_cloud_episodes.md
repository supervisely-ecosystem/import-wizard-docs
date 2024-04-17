<h1 align="left" style="border-bottom: 0"> <img align="left" src="https://github.com/supervisely-ecosystem/import-wizard-docs/assets/48913536/0b32d949-31c9-49f2-b52f-e6337cc3e46b" width="80" style="padding-right: 20px;"> Point Cloud Episodes </h1>

# Overview

This option allows you to upload point clouds as episodes to the platform without any annotations. All items from the input directory and its subdirectories will be uploaded to a single dataset. If you need to preserve the directory structure, you can use the <a href="https://ecosystem.supervisely.com/apps/import-pointcloud-episode" target="_blank">Import Pointcloud Episodes</a> application from the Supervisely Ecosystem.

# Format description

**Supported image formats:** `.pcd`.<br>
**With annotations:** No<br>
**Supported annotation format:** Not applicable.<br>
**Grouped by:** Any structure (will be uploaded to a single dataset).<br>

# Input files structure

Example data: [download ⬇️](https://github.com/supervisely-ecosystem/import-pointcloud-episode/files/12546714/my_pointcloud_episodes_project.zip)<br>

Recommended directory structure:

```text
📦folder
┣ 📦item_01.pcd
┣ 📦item_02.pcd
┣ 📦item_03.pcd
┣ 📦item_04.pcd
┣ 📦item_05.pcd
┣ 📦item_06.pcd
┣ 📦item_07.pcd
┣ 📦item_08.pcd
┣ 📦item_09.pcd
┗ 📦item_10.pcd
```

# Useful links

- <a href="https://ecosystem.supervisely.com/apps/import-pointcloud-episode" target="_blank">[Supervisely Ecosystem] Import Pointcloud Episodes</a>
