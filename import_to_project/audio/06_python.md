# Python SDK

### Description

Integrate your workflow with Supervisely or automate processes using Python SDK.

### Overview

To get started, install <a href="https://pypi.org/project/supervisely/" target="_blank">Supervisely Python SDK</a>:

```bash
pip install supervisely
```

An integration example (find more in our <a href="https://developer.supervisely.com/" target="_blank">Developer portal</a>):

```python
# upload recordings
audio_info = api.audio.upload_path(<dataset_id>, name="engine.wav", path="audio/engine.wav")
# or download a recording
api.audio.download_path(audio_info.id, "audio/engine.wav")

# Update project meta
project_meta = sly.ProjectMeta.from_json(api.project.get_meta(<project_id>))
knock_tag = sly.TagMeta("engine_knock", sly.TagValueType.NONE)
project_meta = project_meta.add_tag_meta(knock_tag)
api.project.update_meta(<project_id>, project_meta)
tag_id = api.project.get_meta(<project_id>)["tags"][0]["id"]

# Label samples 16000..31999 (inclusive) of channel 1:
segment = sly.AudioSegment(tag_id=tag_id, start=16000, end=31999, channel=1)
api.audio.add_segments(<project_id>, audio_info.id, [segment])

# Or upload a whole project in Supervisely format as a new project:
sly.upload_audio_project("path/to/project", api, <workspace_id>)
```
