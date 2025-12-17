---
doc-id: {GENERATE_UUID}
title: {ASSET_NAME}
description: {ASSET_DESCRIPTION}
aurora-mode: {MODE}
tags: [asset, {ASSET_TYPE}, {TAGS}]
created: {DATE}
updated: {DATE}
author: {AUTHOR}
asset:
  filename: {FILENAME}
  type: {TYPE}
  mime-type: {MIME_TYPE}
  size-bytes: {SIZE}
  path: ./assets/{FILENAME}
source:
  origin: {ORIGIN}
  tool: {TOOL}
  license: {LICENSE}
---

# {ASSET_NAME}

## Preview

![{ASSET_NAME}]({FILENAME})

*or for non-images:*

[Download {FILENAME}](./assets/{FILENAME})

## Description

{DETAILED_DESCRIPTION}

## Metadata

- **Format**: {FORMAT}
- **Size**: {SIZE_HUMAN}
- **Created**: {DATE}
- **Tool**: {TOOL}

## Usage

Referenced by:
- [[Document-1|Title]][^1]

[^1]: {"rel-type": "illustrates", "doc-id": "{DOC_ID}", "rel-desc": "This asset illustrates concepts in the document"}

## Notes

Additional context about this asset.

---

*Parent: [[{MODE_FOLDER}/TOC|{MODE_NAME}]]*
