# Supervisely Format

# Overview

Easiest way to import your audio with annotations is to use the Supervisely format.
Check out the <a href="https://docs.supervisely.com/data-organization/00_ann_format_navi" target="_blank">Supervisely JSON format</a> documentation for more details.

In an audio project a label is a tag applied to a range of samples of a recording, optionally about one channel. Each recording has a corresponding annotation `.json` file. The spectrogram settings the recordings are analysed under belong to the project and are stored in `meta.json`.

# Format description

**Supported audio formats:** `.wav`, `.flac`, `.mp3`, `.ogg`, `.m4a`<br>
**With annotations:** Yes<br>
**Supported annotation format:** `.json`.<br>
**Data structure:** Information is provided below.

# Input files structure

Both directory and archive are supported. Each dataset is a directory with `audio` and `ann` subdirectories. Nested datasets are stored in a `datasets` subdirectory of the parent dataset.

**Recommended directory structure:**

```text
📦 project_name
├── 📂 dataset_name
│   ├── 📂 audio
│   │   ├── 🎵 recording_01.wav
│   │   └── 🎵 recording_02.flac
│   ├── 📂 ann
│   │   ├── 📜 recording_01.wav.json
│   │   └── 📜 recording_02.flac.json
│   └── 📂 datasets
│       └── 📂 nested_dataset_name
│           ├── 📂 audio
│           └── 📂 ann
└── 📄 meta.json
```

Project meta file `meta.json` contains tag definitions and project settings. Learn more about the `meta.json` file [here](https://docs.supervisely.com/customization-and-integration/00_ann_format_navi/02_project_classes_and_tags).

# Annotation file

Each recording has a corresponding annotation file named after it, e.g. `recording_01.wav.json`.

```json
{
  "description": "",
  "sampleCount": 160000,
  "sampleRate": 16000,
  "channels": 2,
  "tags": [
    {
      "name": "engine_knock",
      "frameRange": [16000, 31999],
      "channel": 1
    },
    {
      "name": "speaker",
      "frameRange": [40000, 55999],
      "channel": null,
      "value": "driver"
    }
  ]
}
```

**Fields definitions:**

- `sampleCount`, `sampleRate`, `channels` — shape of the recording. The platform does not store them; they are written on export and are optional on import
- `tags` — segment labels of the recording
- `name` — name of the tag from `meta.json`
- `frameRange` — first and last sample of the segment, **both inclusive**, as zero-based indices into the original recording. At 16 kHz, `[16000, 31999]` is the second second of audio
- `channel` — zero-based channel the label is about, or `null` for all channels
- `value` — tag value, for tags that have one
- `meta`, `tagId`, `id`, `labelerLogin` and other server-side fields are written on export and are optional on import. `meta` is kept as is; ids are replaced with the ones of the destination project

# Spectrogram settings

`meta.json` carries the project's spectrogram settings in `projectSettings.spectrogram`:

```json
{
  "classes": [],
  "tags": [
    { "name": "engine_knock", "value_type": "none", "color": "#148A0F" },
    { "name": "speaker", "value_type": "any_string", "color": "#0F8A6E" }
  ],
  "projectType": "audio",
  "projectSettings": {
    "multiView": { "enabled": false, "tagName": null, "tagId": null, "isSynced": false },
    "spectrogram": {
      "scale": "mel",
      "fftSize": 1024,
      "hopLength": 256,
      "window": "hann",
      "melBands": 64,
      "minDb": -100.0,
      "maxDb": 0.0,
      "colormap": "magma",
      "interpolation": "sharp"
    }
  }
}
```

`projectSettings` can be left out entirely. When it is present, its `multiView` block is required, as in every Supervisely project.

The spectrogram settings are applied only when the destination project has no spectrogram settings yet and contains no recordings. A project that is already configured, or already has recordings, keeps its own settings: changing them would change what its existing labels mean. The import log says when the imported settings differ.
