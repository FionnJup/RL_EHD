# Upload Plan

This folder contains the non-code material prepared for the first GitHub upload.

## Included in this upload

- repository documentation;
- license file;
- citation metadata;
- dependency list;
- code availability statement;
- open-source checklist;
- GitHub issue template;
- released result CSV files and trained actor weights.

## Not included in this upload

This folder intentionally does not contain:

```text
code/
```

After this folder is uploaded, the remaining step is to upload the cleaned source-code folder:

```text
github_release/code/
```

Do not upload the original `code/` directory directly, because it may contain generated OpenFOAM runtime or compiled artifacts. Use the cleaned copy in `github_release/code/`.
