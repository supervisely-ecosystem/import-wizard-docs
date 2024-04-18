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
  <b style="font-weight: 600; flex: none;" class="mr5">Video formats:</b>
  <span><code>.avi</code>, <code>.mp4</code>, <code>.3gp</code>, <code>.flv</code>, <code>.webm</code>, <code>.wmv</code>, <code>.mov</code>, <code>.mkv</code></span>

<b style="font-weight: 600; flex: none;" class="mr5">Annotation formats:</b>
<span>
<a href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/videos/videos.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Videos</a><span> | </span>
<a href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/videos/supervisely.md" data-key="sly-open-modal" data-modal-event="open-md-modal" >Supervisely</a><span> | </span>
DAVIS (coming soon)<span> | </span>
MOT (coming soon)
</span>

<b style="font-weight: 600; flex: none;" class="mr5">File size limit:</b>

  <div>
    <div>Community Free plan: 100MB</div>
    <div>Community Pro plan: 500MB</div>
    <div>Enterprise Edition: Unlimited</div>
  </div>
</div>
