# Zotero Reader for Obsidian

An Obsidian plugin for reading and annotating PDF, EPUB, and HTML documents.

This project is based on [duanxianpi/obsidian-zotero-reader-plugin](https://github.com/duanxianpi/obsidian-zotero-reader-plugin). The original project is no longer actively maintained. This fork focuses on making annotation storage more robust by moving annotation-related metadata out of the note body, then adding synchronization fixes and a few quality-of-life improvements on top.

## Installation

Manual installation:

1. Download the contents of this repository.
2. Place them in your Obsidian vault under:
   `.obsidian/plugins/zotero-reader-for-obsidian`
3. Reload Obsidian and enable the plugin.

## How It Works

The plugin does not work on a PDF, EPUB, or HTML file directly. Instead, it uses a Markdown note as the entry point. That note must contain a `source` field in its frontmatter.

Minimal example:

```md
---
source: Papers/MyPaper.pdf
---
```

`source` can be:

- A file path inside the vault
- A wikilink
- A Markdown link
- An `http://` or `https://` URL

Typical workflow:

1. Create a Markdown note.
2. Add `source` in the frontmatter.
3. Open the note and enter Reader mode with the plugin button.
4. Read and annotate in the Reader.
5. Annotation content is written back to the note together with links that jump back to the corresponding location in the Reader.

## What This Version Improves

- Annotation text is written back to the note for easier reading and organization.
- Annotation metadata and reader state are stored separately, so they no longer depend heavily on fragile note-body formatting.
- Removing an annotation callout from the note also cleans up the corresponding stored metadata.
- Clicking an annotation link in the note jumps back to the related reading position.

## Notes

- The `source` field is required for a note to be recognized as a Reader note.
- You can edit the note body freely.
- If you remove an annotation callout or its link from the note, the plugin will treat that annotation as removed and clean up the related stored metadata.

## Acknowledgements

Thanks to the original author [duanxianpi](https://github.com/duanxianpi) for the foundation of this project.
