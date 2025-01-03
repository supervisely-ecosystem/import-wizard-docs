# Cloud Storage

### Description

Import data from connected cloud storage, such as AWS S3, Google Cloud or Azure, with auto-detection of format.

### Overview

Import data from connected cloud storages without re-uploading it to Supervisely. Useful for large datasets.

Select folders or files and press `Run`. Supervisely will detect data format, convert, if needed, and import it to Supervisely. Learn how to connect cloud storage <a href="https://docs.supervisely.com/enterprise-edition/advanced-tuning/s3" target="_blank">here</a>.

<div style="display: grid; grid-template-columns: auto 1fr; grid-column-gap: 5px; grid-row-gap: 10px; grid-auto-rows: auto;">
  <b style="font-weight: 600; flex: none;" class="mr5">Providers:</b>
  <span>AWS S3, Google Cloud Storage, Azure Blob Storage, File System.</span>
  <b style="font-weight: 600; flex: none;" class="mr5">Point clouds format:</b>
  <span><code>.pcd</code></span>

<b style="font-weight: 600; flex: none;" class="mr5">Annotation formats:</b>
<span>
<a href="https://docs.supervisely.com/import-and-export/import/supported-formats-pointcloud/point_clouds" data-modal-href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/point_cloud/point_clouds.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >PCD, PLY, LAS, LAZ format point clouds</a><span> | </span>
<a href="https://docs.supervisely.com/import-and-export/import/supported-formats-pointcloud/supervisely" data-modal-href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/point_cloud/supervisely.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Supervisely format</a><span> | </span>
<a href="https://docs.supervisely.com/import-and-export/import/supported-formats-pointcloud/lyft" data-modal-href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/point_cloud/lyft.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Lyft format</a>
</span>

</div>
