# Cloud Computing Book Mapping

This repository contains the LaTeX source (and supporting assets) for the **Cloud Computing Book Mapping** document.  
The compiled PDF can be tracked in Git if you want convenient distribution, or excluded and produced via local build/CI.

---

## Repository Structure

- `cloud-computing-book-mapping.tex` — Main LaTeX source
- `cloud-computing-book-mapping.pdf` — Compiled output (optional to track)
- `original/` — Source/reference material (e.g., original PDF)

---

## Prerequisites

You need a LaTeX distribution installed.

### Windows
- MiKTeX or TeX Live

### macOS
- MacTeX

### Linux (Debian/Ubuntu example)
- TeX Live packages (e.g., `texlive`, `texlive-latex-extra`, `latexmk`)

---

## Build

### Option A (recommended): `latexmk`
`latexmk` automatically runs the required passes (TOC, references) and handles rebuilds cleanly.

```bash
latexmk -pdf cloud-computing-book-mapping.tex
````

To force a full rebuild:

```bash
latexmk -C
latexmk -pdf cloud-computing-book-mapping.tex
```

### Option B: `pdflatex` (manual)

If you prefer not to use `latexmk`, run `pdflatex` twice to ensure the table of contents is correct:

```bash
pdflatex cloud-computing-book-mapping.tex
pdflatex cloud-computing-book-mapping.tex
```

---

## Cleaning Build Artifacts

If you use `latexmk`:

```bash
latexmk -C
```

Or manually remove common artifacts:

```bash
rm -f *.aux *.log *.out *.toc *.fls *.fdb_latexmk *.synctex.gz
```

---

## Git Ignore Policy

This repo is configured to ignore LaTeX build artifacts (e.g., `.aux`, `.log`, `.toc`).
Whether you track `cloud-computing-book-mapping.pdf` in Git is a project choice:

* **Track the PDF** if you want “clone and open” convenience.
* **Do not track the PDF** if you prefer reproducible builds only (recommended for large docs / frequent changes).

If you decide not to track PDFs, ensure `*.pdf` is uncommented in `.gitignore`.

---

## Suggested Workflow

1. Edit `cloud-computing-book-mapping.tex`
2. Build with `latexmk -pdf cloud-computing-book-mapping.tex`
3. Commit changes to the `.tex` (and optionally the `.pdf`)
4. Push to GitHub

---

## License

Add a LICENSE file if you intend to open-source this repository.

```

If you tell me which direction you want (track the compiled PDF in Git or not), I can also give you the exact `.gitignore` tweak and the one-time cleanup commands to align the repo with that choice.
```
