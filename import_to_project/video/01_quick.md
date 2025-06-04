# Quick

### Description

Upload videos or labeled data from your computer with auto-detection of annotation format.

### Overview

Drag and drop files, folders or an archive. Supervisely will automatically detect annotation format, verify, and import your data.
When uploading to an existing project, Supervisely will automatically validate and merge classes, tags, and annotations.

<div style="display: grid; grid-template-columns: auto 1fr; grid-column-gap: 5px; grid-row-gap: 10px; grid-auto-rows: auto;">
  <b style="font-weight: 600; flex: none;" class="mr5">Video formats:</b>
  <span><code>.avi</code>, <code>.mp4</code>, <code>.3gp</code>, <code>.flv</code>, <code>.webm</code>, <code>.wmv</code>, <code>.mov</code>, <code>.mkv</code></span>

  <b style="font-weight: 600; flex: none;" class="mr5">Codecs:</b>
  <span>
    Any codec is supported; videos are automatically converted to <code>H.264</code> (video) and <code>AAC</code> (audio)
  </span>

  <b style="font-weight: 600; flex: none;" class="mr5">Annotation formats:</b>
  <span>
    <a href="https://docs.supervisely.com/import-and-export/import/import-using-web-ui" data-modal-href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/videos/videos.md" data-key="sly-open-modal" data-modal-event="open-md-modal">Videos</a><span> | </span>
    <a href="https://docs.supervisely.com/import-and-export/import/supported-annotation-formats/videos/supervisely" data-modal-href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/converter_docs/videos/supervisely.md" data-key="sly-open-modal" data-modal-event="open-md-modal">Supervisely</a><span> | </span>
    DAVIS (coming soon)<span> | </span>
    MOT (coming soon)
  </span>

  <div class="entity-size-limits-row"></div><div></div>
</div>
