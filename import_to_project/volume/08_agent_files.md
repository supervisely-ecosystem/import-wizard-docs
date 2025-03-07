# Agent Files

### Description

Import data to Sueprvisely from your agent (local machine, server, etc).

### Overview

If you have a large amount of data on your computer that you want to upload, you can connect your machine to Supervisely and symlink or simply copy these data into a specific directory on your computer that is mounted to the agent. They will then appear in Team Files -> Supervisely Agents.
From there, you can select your data, and the auto-import application will upload them to Supervisely.

> If you don't have any agent, you can connect your computer with GPU to the platform and use it for model training, inference, and evaluation ✨ for FREE. It is as simple as running a single command in the terminal on your machine. Check out our YouTube tutorials: for <a href="https://www.youtube.com/watch?v=WR9qrPTn2X8" target="_blank">Windows</a> or <a href="https://www.youtube.com/watch?v=aO7Zc4kTrVg" target="_blank">Linux/MacOS</a>.

Select folder or an archive with data within your agent folder and press the RUN button. Supervisely will handle the rest: detecting the data format, validating, and uploading.
When uploading to an existing project, Supervisely will automatically validate and merge classes, tags, and annotations.

<div style="display: grid; grid-template-columns: auto 1fr; grid-column-gap: 5px; grid-row-gap: 10px; grid-auto-rows: auto;">
  <b style="font-weight: 600; flex: none;" class="mr5">Volume formats:</b>
  <span><code>.nrrd</code>, <code>.dcm</code>, <code>.nii</code>, <code>.nii.gz</code></span>

<b style="font-weight: 600; flex: none;" class="mr5">Annotation formats:</b>
<span>
<a href="https://docs.supervisely.com/import-and-export/import/supported-annotation-formats/volumes/nifti" data-modal-href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/volumes/nifti.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >NIfTI</a><span> | </span>
<a href="https://docs.supervisely.com/import-and-export/import/supported-annotation-formats/volumes/nifti" data-modal-href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/volumes/nifti.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >NifTI Instance & Semantic segmentation</a><span> | </span>
<a href="https://docs.supervisely.com/import-and-export/import/supported-annotation-formats/volumes/supervisely" data-modal-href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/volumes/supervisely.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Supervisely</a><span> | </span>
<a href="https://docs.supervisely.com/import-and-export/import/supported-annotation-formats/volumes/volumes" data-modal-href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/volumes/volumes.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >NRRD, DICOM files</a>
</span>

<b style="font-weight: 600; flex: none;" class="mr5">File size limit:</b>

<div>
    <div>Community Free plan: <i style="color:rgb(53, 53, 53); font-size: 12px">max</i> <b>150</b> <i style="color:rgb(53, 53, 53); font-size: 12px">MB per volume</i></div>
    <div>Community Pro plan: <i style="color:rgb(53, 53, 53); font-size: 12px">max</i> <b>150</b> <i style="color:rgb(53, 53, 53); font-size: 12px">MB per volume</i></div>
    <div>Enterprise Edition: <b>Unlimited</b></div>
</div>
</div>
