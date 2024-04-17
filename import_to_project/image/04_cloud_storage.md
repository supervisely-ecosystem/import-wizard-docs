# Cloud Storage

### Description

Import data from connected cloud storage, such as AWS S3, Google Cloud or Azure, with auto-detection of format.

### Overview

✨ _Available in Enterprise Edition._

Import data from connected cloud storage without re-uploading it to Supervisely. Useful for large datasets.

Select folders or files and press `Run`. Supervisely will detect data format, convert, if needed, and import it to Supervisely. Learn how to connect cloud storage <a href="https://docs.supervisely.com/enterprise-edition/advanced-tuning/s3" target="_blank">here</a>.

<div style="display: grid; grid-template-columns: auto 1fr; grid-column-gap: 5px; grid-row-gap: 10px; grid-auto-rows: auto;">
  <b style="font-weight: 600; flex: none;" class="mr5">Providers:</b>
  <span>AWS S3, Google Cloud Storage, Azure Blob Storage, File System.</span>
  <b style="font-weight: 600; flex: none;" class="mr5">Image formats:</b>
  <span><code>.jpg</code>, <code>.jpeg</code>, <code>.mpo</code>, <code>.bmp</code>, <code>.png</code>, <code>.webp</code>, <code>.tiff</code>, <code>.tif</code>, <code>.nrrd</code>, <code>.jfif</code>, <code>.avif</code>, <code>.heic</code>, <code>NIfTI and DICOM</code></span>

<b style="font-weight: 600; flex: none;" class="mr5">Annotation formats:</b>
<span>
Images in any directory structure without annotations<span> | </span>
<a href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/supervisely.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Supervisely</a><span> | </span>
<a href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/coco.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >COCO</a><span> | </span>
<a href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/yolo.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >YOLO</a><span> | </span>
<a href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/pascal.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Pascal VOC</a><span> | </span>
<a href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/cityscapes.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Cityscapes</a><span> | </span>
<a href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/masks.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Images with masks</a><span> | </span>
<a href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/multiview.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Multi-view images</a><span> | </span>
<a href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/multispectral.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Multispectral images</a><span> | </span>
<a href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/medical_2d.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Medical 2D (single)</a><span> | </span>
<a href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/csv.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Links from CSV or TXT</a><span> | </span>
<a href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/pdf.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >PDFs pages as images</a>
</span>

<b style="font-weight: 600; flex: none;" class="mr5">File size limit:</b>

  <div>
    <div>Community Free plan: 25MB</div>
    <div>Community Pro plan: 300MB</div>
    <div>Enterprise Edition: Unlimited</div>
  </div>
</div>
