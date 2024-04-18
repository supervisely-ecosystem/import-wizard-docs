# Agent Files

### Description

Import data to Sueprvisely from your agent (local machine, server, etc).

### Overview

If you have a large amount of data on your computer that you want to upload, you can connect your machine to Supervisely and symlink or simply copy these data into a specific directory on your computer that is mounted to the agent. They will then appear in Team Files → Supervisely Agents.
From there, you can select your data, and the auto-import application will upload them to Supervisely.

> If you don't have any agent, you can connect your computer with GPU to the platform and use it for model training, inference, and evaluation ✨ for FREE. It is as simple as running a single command in the terminal on your machine. Check out our YouTube tutorials: for <a href="https://www.youtube.com/watch?v=WR9qrPTn2X8" target="_blank">Windows</a> or <a href="https://www.youtube.com/watch?v=aO7Zc4kTrVg" target="_blank">Linux/MacOS</a>.

Select folder or an archive with data within your agent folder and press the RUN button. Supervisely will handle the rest: detecting the data format, validating, and uploading to Supervisely.
When uploading to an existing project, Supervisely will automatically validate and merge classes, tags, and annotations.

<div style="display: grid; grid-template-columns: auto 1fr; grid-column-gap: 5px; grid-row-gap: 10px; grid-auto-rows: auto;">
  <b style="font-weight: 600; flex: none;" class="mr5">Image formats:</b>
  <span><code>.jpg</code>, <code>.jpeg</code>, <code>.mpo</code>, <code>.bmp</code>, <code>.png</code>, <code>.webp</code>, <code>.tiff</code>, <code>.tif</code>, <code>.nrrd</code>, <code>.jfif</code>, <code>.avif</code>, <code>.heic</code>, <code>NIfTI</code>, <code>DICOM</code></span>

<b style="font-weight: 600; flex: none;" class="mr5">Annotation formats:</b>
<span>
<a href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/images/images.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Images</a><span> | </span>
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
