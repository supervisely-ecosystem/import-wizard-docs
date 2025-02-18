# Cloud Storage

### Description

Import data from connected cloud storage, such as AWS S3, Google Cloud or Azure, with auto-detection of format.

### Overview

Import data from connected cloud storage without re-uploading it to Supervisely. Useful for large datasets.

Select folders or files and press `Run`. Supervisely will detect data format, convert, if needed, and import it to Supervisely. Learn how to connect cloud storage <a href="https://docs.supervisely.com/enterprise-edition/advanced-tuning/s3" target="_blank">here</a>.

<div style="display: grid; grid-template-columns: auto 1fr; grid-column-gap: 5px; grid-row-gap: 10px; grid-auto-rows: auto;">
  <b style="font-weight: 600; flex: none;" class="mr5">Providers:</b>
  <span>AWS S3, Google Cloud Storage, Azure Blob Storage, File System.</span>
  <b style="font-weight: 600; flex: none;" class="mr5">Supported volume formats:</b>
  <span><code>.nrrd</code>, <code>.dcm</code></span>

<b style="font-weight: 600; flex: none;" class="mr5">Annotation formats:</b>
<span>
<a href="https://github.com/supervisely-ecosystem/import-wizard-docs/blob/master/converter_docs/volumes/volumes.md" data-modal-href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/volumes/volumes.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Volumes (NRRD, DICOM files)</a><span> | </span>
<a href="https://github.com/supervisely-ecosystem/import-wizard-docs/blob/master/converter_docs/volumes/supervisely.md" data-modal-href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/volumes/supervisely.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Supervisely</a>
</span>

<b style="font-weight: 600; flex: none;" class="mr5">File size limit:</b>

<div>
    <div>Community Free plan: <i style="color:rgb(53, 53, 53); font-size: 12px">max</i> <b>150</b> <i style="color:rgb(53, 53, 53); font-size: 12px">MB per volume</i></div>
    <div>Community Pro plan: <i style="color:rgb(53, 53, 53); font-size: 12px">max</i> <b>150</b> <i style="color:rgb(53, 53, 53); font-size: 12px">MB per volume</i></div>
    <div>Enterprise Edition: <b>Unlimited</b></div>
</div>
</div>
