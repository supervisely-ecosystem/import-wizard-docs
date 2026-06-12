---
applyTo: "**/*.md"
---

# Instructions: Import Wizard Documentation

This workspace contains documentation for the Supervisely **Import Wizard** feature.
When creating or editing any Markdown file here, follow all conventions from the domain knowledge file:

**Always read the skill file before creating or editing any doc:**
[SKILL.md](../SKILL.md)

---

## Quick Reference

### Which file type am I working on?

| Path pattern | Doc type | Key rules |
|---|---|---|
| `import_to_project/{modality}/NN_*.md` | Import method doc | §4 of SKILL.md |
| `converter_docs/{modality}/*.md` | Format/converter doc | §5 of SKILL.md |
| `create_project/{modality}/*.md` | Project settings desc | §6 of SKILL.md |

---

### Creating a new modality in `import_to_project`

Always create exactly **11 files** numbered `01_` through `11_`. Use the fixed file names and titles from SKILL.md §4. For files `01`, `04`, `08`, `09` include the HTML format grid (SKILL.md §4.1). For files `05`, `06`, `07` include the appropriate code blocks (SKILL.md §4.2). After creating the files, add the modality `<details>` block to `README.md` (SKILL.md §7).

### Creating a new converter doc

Use the template in SKILL.md §5. Include:
- Optional logo `<h1>` header if the format has a public logo
- `# Overview` — what the format is and what the converter does
- `# Format description` — supported file extensions, with/without annotations
- `# Input files structure` — example download link + directory tree with emoji (SKILL.md §5.1)
- `# Useful links` — links to Supervisely Ecosystem apps if applicable

### Annotation format links in `import_to_project` files

Every reference to a converter doc must use the modal link pattern from SKILL.md §8 — **never** a plain markdown link inside the HTML grid.

---

## Checklist before saving a new doc

- [ ] Title matches the convention table in SKILL.md §4 (for import method docs)
- [ ] `### Description` is a single sentence
- [ ] `### Overview` is 2–4 sentences
- [ ] All annotation format links use `data-key="sly-open-modal"` and `data-modal-event="open-md-modal"`
- [ ] `data-modal-href` points to the correct raw GitHub URL
- [ ] HTML format grid ends with `<div class="entity-size-limits-row"></div><div></div>`
- [ ] Directory tree uses correct emoji from SKILL.md §5.1
- [ ] External links use `target="_blank"`
- [ ] No H2 headings in `import_to_project` files
