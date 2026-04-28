# BUW (ROSES) Thesis Proposal / Exposé Template

LaTeX template for Bachelor's and Master's thesis proposals (Exposés) at the
University of Wuppertal, research group **Robust, Secure and Privacy-Preserving
Smart Systems (ROSES)**.

## Quick start

1. Open this repository in VSCode with the *Dev Containers* extension and re-open in container —
   the devcontainer ships with TeX Live, latexmk, the LTeX grammar/spell checker and an inline PDF viewer.
2. Edit [`settings.tex`](settings.tex) — title, author, examiners, dates, toggles.
3. Edit [`chapters/timeline.tex`](chapters/timeline.tex) and comment out either
   `ba-ganttchart` or `ma-ganttchart`, depending on whether your thesis is a Bachelor's or Master's.
4. Write your chapters in [`chapters/`](chapters/) and your bibliography in [`literature/literature.bib`](literature/literature.bib).
5. Save any `.tex` file — the container builds the PDF automatically.

## Repository layout

| Path | Purpose |
|---|---|
| [`exposee.tex`](exposee.tex) | Main entry point. Lists which chapters are included. |
| [`settings.tex`](settings.tex) | All exposé-specific values and layout toggles (edit this). |
| [`template/`](template/) | Title page, declaration of authorship + AI-tools form, header/footer, bibliography, Gantt-chart styling. **Do not edit unless you know what you are doing.** |
| [`chapters/`](chapters/) | One file per chapter (intro, work packages, thesis structure, timeline, plus Bachelor/Master Gantt variants). |
| [`glossary/glossary.tex`](glossary/glossary.tex) | Acronyms and glossary entries (used inline via `\gls{}`; not printed). |
| [`literature/literature.bib`](literature/literature.bib) | BibTeX bibliography. |
| [`images/`](images/) | BUW logos (color, grayscale, rich black). |
| [`examples/`](examples/) | Reference exposés from previous students. |

## Building manually

```sh
latexmk --shell-escape -synctex=1 -pdf exposee.tex
```

`--shell-escape` is required because the template uses [`minted`](https://github.com/gpoore/minted) for code listings.

## Origin

This template was originally based on the [RUB-NDS exposé template](https://github.com/RUB-NDS/exposee_layout)
and was migrated to the BUW corporate design, sharing the layout logic (preamble, header/footer, title page)
with the [BUW thesis template](https://github.com/CheariX/thesis_layout).
