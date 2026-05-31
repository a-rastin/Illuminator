# Lumindra v2.0.0

Colab-ready PDF analysis notebook that detects page content (titles, text, tables, images, page numbers, footnotes), annotates the PDF with colored bounding boxes, and exports a table-of-contents markdown file.

## Quick start (Google Colab)

1. Upload [`Lumindra_v2.0.0.ipynb`](Lumindra_v2.0.0.ipynb) to Google Colab (or open from Drive).
2. **Runtime → Run all** (first run installs dependencies and downloads Docling models; may take several minutes).
3. Upload your PDF when prompted.
4. Download **`Output.zip`**, which contains:
   - Annotated PDF (`annotated.pdf`)
   - `Table_of_content.md`

## Requirements

- A **true PDF** (text/lvector-based; scanned PDFs may have limited accuracy).
- Google Colab runtime (recommended) or local Jupyter with Python 3.10+.

## Tools used

- [Docling](https://github.com/docling-project/docling) — layout analysis and content classification
- [PyMuPDF](https://github.com/pymupdf/PyMuPDF) — PDF I/O, orientation detection, annotation
- [Camelot](https://github.com/camelot-dev/camelot) (stream flavor) — table bounding-box refinement

## Output numbering

Each detected item receives:

- A **global** sequential number across the document
- A **per-type** counter shown in parentheses (Title, Subtitle, Subsubtitle, Text, Table, Picture, Page number, Footnote)
