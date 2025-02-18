# Cloud Storage

### Description

Import data from connected cloud storage, such as AWS S3, Google Cloud or Azure, with auto-detection of format.

### Overview

Import data from connected cloud storage without re-uploading it to Supervisely. Useful for large datasets.

Select folders or files and press `Run`. Supervisely will detect data format, convert, if needed, and import it to Supervisely. Learn how to connect cloud storage <a href="https://docs.supervisely.com/enterprise-edition/advanced-tuning/s3" target="_blank">here</a>.

<div style="display: grid; grid-template-columns: auto 1fr; grid-column-gap: 5px; grid-row-gap: 10px; grid-auto-rows: auto;">
  <b style="font-weight: 600; flex: none;" class="mr5">Providers:</b>
  <span>AWS S3, Google Cloud Storage, Azure Blob Storage, File System</span>
  <b style="font-weight: 600; flex: none;" class="mr5">Video formats:</b>
  <span><code>.avi</code>, <code>.mp4</code>, <code>.3gp</code>, <code>.flv</code>, <code>.webm</code>, <code>.wmv</code>, <code>.mov</code>, <code>.mkv</code></span>

<b style="font-weight: 600; flex: none;" class="mr5">Annotation formats:</b>
<span>
<a href="https://docs.supervisely.com/import-and-export/import/import-using-web-ui" data-modal-href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/videos/videos.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Videos</a><span> | </span>
<a href="https://docs.supervisely.com/import-and-export/import/supported-annotation-formats/videos/supervisely" data-modal-href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/videos/supervisely.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Supervisely</a><span> | </span>
DAVIS (coming soon)<span> | </span>
MOT (coming soon)
</span>

<b style="font-weight: 600; flex: none;" class="mr5">Video size limit:</b>

<div>
    <div>Community Free plan: <i style="color:rgb(53, 53, 53); font-size: 12px">max</i> <b>100</b> <i style="color:rgb(53, 53, 53); font-size: 12px">MB per video</i></div>
    <div>Community Pro plan: <i style="color:rgb(53, 53, 53); font-size: 12px">max</i> <b>500</b> <i style="color:rgb(53, 53, 53); font-size: 12px">MB per video</i></div>
    <div>Enterprise Edition: <b>Unlimited</b>  <i style="color:rgb(53, 53, 53); font-size: 12px">(video size, resolution, etc.)</i></div>
</div>
