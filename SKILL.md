# Import Wizard Docs — Domain Knowledge & Templates

This file contains all conventions, templates, and patterns for creating documentation in this repository.

---

## 1. Project Overview

This repository documents the **Supervisely Import Wizard** — a feature for importing data (images, videos, volumes, point clouds, point cloud episodes) into the Supervisely platform.

**GitHub repository URL base (for raw links):**
`https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/`

**Docs site base URL:**
`https://docs.supervisely.com/import-and-export/import/`

---

## 2. Repository Structure

```
import-wizard-docs/
├── import_to_project/          # Import method docs per modality
│   ├── image/                  # 01–11 numbered files
│   ├── video/
│   ├── volume/
│   ├── point_cloud/
│   ├── point_cloud_episodes/
│   └── legacy/                 # Old format (do not create new files here)
├── converter_docs/             # Format/converter reference docs per modality
│   ├── images/
│   ├── videos/
│   ├── volumes/
│   ├── point_cloud/
│   └── point_cloud_episodes/
└── create_project/             # Project settings descriptions per modality
    ├── images/                 # 01–07 numbered files
    └── point_clouds/
```

---

## 3. File Naming Conventions

- `import_to_project/{modality}/` — always **11 files** with prefix `01_` through `11_`:
  - `01_quick.md`
  - `02_import_apps.md`
  - `03_link_remote_data.md`
  - `04_cloud_storage.md`
  - `05_cli.md`
  - `06_python.md`
  - `07_http_api.md`
  - `08_agent_files.md`
  - `09_team_files.md`
  - `10_migration.md`
  - `11_custom.md`
- `converter_docs/{modality}/` — named after the format (e.g., `coco.md`, `yolo.md`, `supervisely.md`)
- `create_project/{modality}/` — numbered files prefixed `01_`, `02_`, etc.

---

## 4. `import_to_project` File Format

### Structure (all files)

```markdown
# {Title}

### Description

{One sentence that describes what this import method does.}

### Overview

{2–4 sentences explaining the method, how to use it, and when it is useful.}

{Optional: HTML format grid — see §4.1}
{Optional: code blocks — see §4.2}
```

### Title mapping

| File                     | Title                                 |
| ------------------------ | ------------------------------------- |
| `01_quick.md`            | `Quick`                               |
| `02_import_apps.md`      | `Supervisely Apps`                    |
| `03_link_remote_data.md` | `Link remote data`                    |
| `04_cloud_storage.md`    | `Cloud Storage`                       |
| `05_cli.md`              | `CLI`                                 |
| `06_python.md`           | `Python SDK`                          |
| `07_http_api.md`         | `API`                                 |
| `08_agent_files.md`      | `Agent Files`                         |
| `09_team_files.md`       | `Team Files`                          |
| `10_migration.md`        | `Migration from other labeling tools` |
| `11_custom.md`           | `Custom`                              |

### 4.1 HTML Format Grid (used in `01_quick`, `04_cloud_storage`, `08_agent_files`, `09_team_files`)

```html
<div
  style="display: grid; grid-template-columns: auto 1fr; grid-column-gap: 5px; grid-row-gap: 10px; grid-auto-rows: auto;"
>
  <b style="font-weight: 600; flex: none;" class="mr5">{Format type label}:</b>
  <span><code>.ext1</code>, <code>.ext2</code>, <code>.ext3</code></span>

  <b style="font-weight: 600; flex: none;" class="mr5">Annotation formats:</b>
  <span>
    <a
      href="{docs_url}"
      data-modal-href="{raw_github_url}"
      data-key="sly-open-modal"
      data-modal-event="open-md-modal"
      >{Format Name}</a
    ><span> | </span>
    <a
      href="{docs_url}"
      data-modal-href="{raw_github_url}"
      data-key="sly-open-modal"
      data-modal-event="open-md-modal"
      >{Format Name}</a
    >
  </span>

  <div class="entity-size-limits-row"></div>
  <div></div>
</div>
```

**Rules for the format grid:**

- `data-modal-href` always points to the raw GitHub URL of the corresponding `converter_docs` file.
- `data-key="sly-open-modal"` and `data-modal-event="open-md-modal"` are required on every annotation link.
- Annotation format links are separated by `<span> | </span>` (including the last one before any plain text).
- `<div class="entity-size-limits-row"></div><div></div>` must appear as the final row of the grid.
- Plain text entries (e.g., `DAVIS (coming soon)`) are not wrapped in `<a>` tags.

**Format type label by modality:**

| Modality             | Label                  |
| -------------------- | ---------------------- |
| Images               | `Image formats:`       |
| Videos               | `Video formats:`       |
| Volumes              | `Volume formats:`      |
| Point Cloud          | `Point cloud formats:` |
| Point Cloud Episodes | `Point cloud formats:` |

**Common supported formats:**

| Modality     | Formats                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------- |
| Images       | `.jpg`, `.jpeg`, `.mpo`, `.bmp`, `.png`, `.webp`, `.tiff`, `.tif`, `.nrrd`, `.jfif`, `.avif`, `.heic`, `NIfTI`, `DICOM`, `.exr`, `.hdr` |
| Videos       | `.avi`, `.mp4`, `.3gp`, `.flv`, `.webm`, `.wmv`, `.mov`, `.mkv`                                                                         |
| Volumes      | `.nrrd`, `.dcm`, `.nii`, `.nii.gz`                                                                                                      |
| Point Clouds | `.pcd`, `.ply`, `.las`, `.laz`                                                                                                          |

**Cloud Storage additional field (only in `04_cloud_storage.md`):**

```html
<b style="font-weight: 600; flex: none;" class="mr5">Providers:</b>
<span>AWS S3, Google Cloud Storage, Azure Blob Storage, File System.</span>
```

This row appears **before** the format row.

### 4.2 Code Blocks (used in `05_cli.md` and `06_python.md`)

**CLI (`05_cli.md`)** — two numbered sections:

```markdown
**1. Supervisely SDK CLI**

First of all, you need to install it:

\`\`\`bash
pip3 install –upgrade supervisely
\`\`\`

Then upload your local project by the single command:

\`\`\`bash
supervisely project upload -s <source-local> -id <workspace-id> -n <project-name>
\`\`\`

To learn more about Supervisely SDK CLI click <a href="https://developer.supervisely.com/getting-started/command-line-interface/sdk-cli" target="_blank">here</a>

**2. Enterprise CLI Tool**

Installation:

\`\`\`bash
sudo curl -fsSL https://config.enterprise.supervisely.com/cli -o /usr/local/bin/supervisely && sudo chmod +x /usr/local/bin/supervisely
\`\`\`

Run this single command to upload your local project:

\`\`\`bash
supervisely instance $entity_type upload-project -p <local_path> -n <project_name> -tid <team_id> -wid <workspace_id>
\`\`\`

To learn more about Enterprise CLI Tool click <a href="https://developer.supervisely.com/getting-started/command-line-interface/cli-tool" target="_blank">here</a>.
```

**Python SDK (`06_python.md`)** — install + code example with a link to Developer Portal.

**API (`07_http_api.md`)** — cURL example + link to `https://api.docs.supervisely.com/`.

---

## 5. `converter_docs` File Format

### Structure

```markdown
<h1 align="left" style="border-bottom: 0"> <img align="left" src="{logo_url}" width="80" style="padding-right: 20px;"> {Format Name} </h1>

# Overview

{Description of the format and what the converter does. 2–4 sentences.}

# Format description

**Supported {data type} formats:** `.ext1`, `.ext2`<br>
**With annotations:** Yes / No<br>
**Supported annotation format:** `.json` / Not applicable.<br>
**Grouped by:** {grouping strategy}.<br>
**Data structure:** Information is provided below. ← (add only if structure is documented below)

# Input files structure

Example data: [download ⬇️]({github_release_or_files_url})

Both directory and archive are supported.

**Recommended directory structure:**

\`\`\`text
{ASCII tree with emoji icons — see §5.1}
\`\`\`

# Useful links

- <a href="{url}" target="_blank">[Supervisely Ecosystem] {App Name}</a>
```

> The `<h1>` logo header is **optional** for formats that do not have a public logo. In that case use a plain `# {Format Name}` heading.

### 5.1 Directory Tree Emoji Icons

| Item type              | Emoji        |
| ---------------------- | ------------ |
| Root archive / project | `📦`         |
| Directory/folder       | `📂`         |
| Image file             | `🖼️` or `🏞️` |
| Video file             | `🎬`         |
| Medical volume         | `🩻`         |
| Point cloud file       | `📄`         |
| JSON / text file       | `📜` or `📄` |

**Tree connectors:**

```
📦 root
├── 📂 folder1
│   ├── 📜 file1.json
│   └── 📜 file2.json
└── 📂 folder2
    └── 📄 data.pcd
```

### 5.2 Per-modality converter doc paths and docs URLs

| Modality     | `converter_docs/` path                            | docs.supervisely.com URL segment                             |
| ------------ | ------------------------------------------------- | ------------------------------------------------------------ |
| Images       | `converter_docs/images/{format}.md`               | `supported-annotation-formats/images/{format}`               |
| Videos       | `converter_docs/videos/{format}.md`               | `supported-annotation-formats/videos/{format}`               |
| Volumes      | `converter_docs/volumes/{format}.md`              | `supported-annotation-formats/volumes/{format}`              |
| Point Clouds | `converter_docs/point_cloud/{format}.md`          | `supported-annotation-formats/pointclouds/{format}`          |
| PC Episodes  | `converter_docs/point_cloud_episodes/{format}.md` | `supported-annotation-formats/point-cloud-episodes/{format}` |

---

## 6. `create_project` File Format

Very short (1–4 sentences). Describes what project settings are applied and why this project type is useful. Can include links to blog posts and videos.

```markdown
{One or two sentence description of the project type and import settings.}

[blog post]({url})

[video]({youtube_url})
```

---

## 7. `README.md` Structure

The README uses `<details>` blocks per modality, each containing a bullet list linking to all 11 import method files.

```markdown
<details>
  <summary>{Modality}</summary>

- [Quick import](import_to_project/{modality}/01_quick.md)
- [Apps from Ecosystem](import_to_project/{modality}/02_import_apps.md)
- [Links](import_to_project/{modality}/03_link_remote_data.md)
- [Cloud Storage](import_to_project/{modality}/04_cloud_storage.md)
- [Command Line Interface (CLI)](import_to_project/{modality}/05_cli.md)
- [Python SDK](import_to_project/{modality}/06_python.md)
- [REST API](import_to_project/{modality}/07_http_api.md)
- [Your Agent](import_to_project/{modality}/08_agent_files.md)
- [Team Files](import_to_project/{modality}/09_team_files.md)
- [Migration from other labeling tool](import_to_project/{modality}/10_migration.md)
- [Custom Import App](import_to_project/{modality}/11_custom.md)

</details>
```

---

## 8. Annotation Format Modal Link Pattern

Every reference to a converter doc (from within `import_to_project` files) must follow this pattern:

```html
<a
  href="{docs_site_url}"
  data-modal-href="https://raw.githubusercontent.com/supervisely-ecosystem/import-wizard-docs/master/{converter_docs_path}"
  data-key="sly-open-modal"
  data-modal-event="open-md-modal"
  >{Display Name}</a
>
```

Note the trailing space before `>` is intentional (matches the project convention).

---

## 9. Key External URLs

| Purpose               | URL                                                                                 |
| --------------------- | ----------------------------------------------------------------------------------- |
| Supervisely Docs      | `https://docs.supervisely.com/`                                                     |
| Developer Portal      | `https://developer.supervisely.com/`                                                |
| Supervisely Ecosystem | `https://ecosystem.supervisely.com/`                                                |
| Supervisely API Docs  | `https://api.docs.supervisely.com/`                                                 |
| Supervisely PyPI      | `https://pypi.org/project/supervisely/`                                             |
| Cloud Storage setup   | `https://docs.supervisely.com/enterprise-edition/advanced-tuning/s3`                |
| SDK CLI docs          | `https://developer.supervisely.com/getting-started/command-line-interface/sdk-cli`  |
| Enterprise CLI docs   | `https://developer.supervisely.com/getting-started/command-line-interface/cli-tool` |

---

## 10. Writing Style Rules

1. **Descriptions** are one sentence, action-oriented (verb first when possible).
2. **Overview** sections are 2–4 sentences. No bullet points unless listing apps or steps.
3. Use `<a ... target="_blank">` for all external links in HTML contexts.
4. In plain markdown, use regular `[text](url)` links.
5. Do **not** use H2 (`##`) inside `import_to_project` files — only `# Title`, `### Description`, `### Overview`.
6. Converter docs use `#` for top-level sections (Overview, Format description, etc.).
7. Format file extensions as `` `.ext` `` in plain markdown, and `<code>.ext</code>` inside HTML spans.
8. Emoji in directory trees follow the mapping in §5.1.
9. "Coming soon" features are plain text (not linked): `FeatureName (coming soon)`.
10. Never add H4+ headings in `import_to_project` docs (keep it flat: H1 title + H3 sections).
