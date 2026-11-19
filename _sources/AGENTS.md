# AGENTS.md

This file provides guidance to Codex (claude.ai/code) when working with code in this repository.

## What this is

Interactive course notes for **Molecular Simulations (0351-4057)** at Tel Aviv University, built with [Jupyter Book](https://jupyterbook.org/). The content is the product — physics/math exposition and pedagogical Python, published to GitHub Pages (https://barakhirshberg.github.io/MolecularSimulations/). There is no application code, library, or test suite; "correctness" here means correct physics, math, prose, and demonstration code that runs and produces sensible output.

## Build & preview

```bash
# environment (conda preferred)
conda env create -f environment.yml && conda activate book
pip install -r requirements.txt          # Jupyter Book toolchain

jupyter-book build .                      # -> _build/html/index.html
rm -rf _build && jupyter-book build .     # clean rebuild
```

Publishing to GitHub Pages is manual:

```bash
jupyter-book build .
ghp-import -n -f _build/html
git push origin gh-pages --force
```

## Architecture & conventions

- **`_toc.yml` defines the book.** Chapter order is pedagogical (theory → project), not alphabetical: `intro` → ClassicalMech → StatMech → MolecularDynamics → ProjPrerequisites → NumProjI → MonteCarlo → NumProjII → NumProjIII. A new notebook is invisible until added here.
- **`_config.yml` sets `execute_notebooks: "off"`.** Notebook outputs are committed and served as-is; the build does **not** re-run cells. This means saved outputs can drift from the code that produced them — if you change a code cell, re-run it in Jupyter and save so the committed output matches, otherwise the published book shows stale results.
- **The notebooks are lecture notes, so most cells are MyST-Markdown**, not code. Math uses `$...$`/`$$...$$` and `amsmath` (enabled via `myst_enable_extensions`). Cross-references use labeled equations/sections, e.g. `$$...$$ (label)` defined and `{eq}`label`` / `[](label)` to cite. When editing, keep labels stable — they are referenced across chapters.
- **`references.bib`** backs citations; `_config.yml` lists it under `bibtex_bibfiles`.
- The `NumProj*.ipynb` notebooks are **student assignments** (MD, Metropolis MC, and an advanced final project). Code demos elsewhere (e.g. MonteCarlo.ipynb) are self-contained teaching examples using only numpy/scipy/matplotlib.

## Editing notes

- Preserve the pedagogical framing: `{admonition}` blocks with `:class: tip` (active-learning prompts) and `:class: dropdown` (worked solutions) are used deliberately throughout — match that style rather than inlining answers.
- The README invites student PRs that fix typos/math/code, one fix per PR. There is a **deliberate typo in `intro.md`** left as a student exercise — do not "fix" it unless explicitly asked.
- Ignore `jupyterbook-env/` and `_build/` (git-ignored build/venv artifacts); never edit generated files under `_build/`.
