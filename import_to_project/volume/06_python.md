# Python SDK

### Description

Integrate your workflow with Supervisely or automate processes using Python SDK.

### Overview

To get started, install Supervisely Python SDK:

```bash
pip install supervisely
```

### Examples

**Upload NRRD format volume**

```python
local_path = "src/upload/nrrd/MRHead.nrrd"

nrrd_info = api.volume.upload_nrrd_serie_path(dataset.id, "MRHead.nrrd", local_path)
```

**Upload volume as NumPy array**

```python
np_volume, meta = sly.volume.read_nrrd_serie_volume_np(local_path)

nrrd_info_np = api.volume.upload_np(dataset.id, "MRHead_np.nrrd", np_volume, meta)
```

**Upload DICOM series from local directory**

```python
dicom_dir_name = "src/upload/MRHead_dicom/"

# Inspect you local directory and collect all dicom series.
series_infos = sly.volume.inspect_dicom_series(root_dir=dicom_dir_name)

# Upload DICOM series from local directory to Supervisely platform.
for serie_id, files in series_infos.items():
    item_path = files[0]
    name = f"{sly.fs.get_file_name(path=item_path)}.nrrd"
    dicom_info = api.volume.upload_dicom_serie_paths(dataset.id, name, files, anonymize=True)
```
