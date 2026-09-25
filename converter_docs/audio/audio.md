# Audio

# Overview

This option allows you to upload audio recordings to the platform without any annotations. All recordings from the input directory and its subdirectories will be uploaded to a single dataset.

# Format description

**Supported audio formats:** `.wav`, `.flac`, `.mp3`, `.ogg`, `.m4a`<br>
**With annotations:** No<br>
**Supported annotation format:** Not applicable.<br>
**Grouped by:** Any structure (will be uploaded as a single dataset).<br>

# Input files structure

Recommended directory structure:

```text
📦 project name
├── 🎵 recording_01.wav
├── 🎵 recording_02.flac
└── 📂 bench_b
    ├── 🎵 recording_03.mp3
    └── 🎵 recording_04.m4a
```

Files with other extensions are skipped.

Audio is always uploaded as files. Importing audio as links is not supported: if the option is selected, the recordings are uploaded anyway.
