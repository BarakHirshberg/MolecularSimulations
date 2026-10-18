# Molecular Simulations - Course Notes

Course notes for **Molecular Simulations (0351-4057)** at Tel Aviv University.

**Author:** Prof. Barak Hirshberg, School of Chemistry, Tel Aviv University

**Website:** https://barakhirshberg.github.io/MolecularSimulations/

## About This Project

This repository contains interactive course materials built using [Jupyter Book](https://jupyterbook.org/). The course covers:

-   Classical mechanics fundamentals
-   Statistical mechanics
-   Molecular Dynamics (MD) simulations
-   Monte Carlo (MC) simulations
-   Hands-on implementation in Python

The materials are based on the authoritative book by Professor Mark E. Tuckerman, [Statistical Mechanics: Theory and Molecular Simulations](https://tau-primo.hosted.exlibrisgroup.com/permalink/f/8560f2/972TAU_ALMA51249053460004146).

## For Developers: Setting Up the Development Environment

### Prerequisites

-   Python 3.11 or higher
-   Git
-   (Optional) Conda for environment management

### Option 1: Using Conda (Recommended)

`environment.yml` installs the full stack — the Jupyter Book toolchain **and**
the scientific libraries used by the notebooks — so this single step is all you
need:

```bash
conda env create -f environment.yml
conda activate book
```

### Option 2: Using pip only

1. **Create a virtual environment**

    ```bash
    python -m venv jupyterbook-env
    source jupyterbook-env/bin/activate  # On Windows: jupyterbook-env\Scripts\activate
    ```

2. **Install dependencies**
    ```bash
    pip install -r requirements.txt
    ```

## Building the Book Locally

After setting up your environment:

1. **Activate your environment**

    ```bash
    conda activate book
    # OR
    source jupyterbook-env/bin/activate
    ```

2. **Build the book**

    ```bash
    jupyter-book build .
    ```

3. **View the book**
    - Open `_build/html/index.html` in your web browser
    - Or use a local server:
        ```bash
        cd _build/html
        python -m http.server 8000
        ```
        Then visit `http://localhost:8000` in your browser

### Clean Build

To remove previous build artifacts and rebuild from scratch:

```bash
rm -rf _build
jupyter-book build .
```

## Project Structure

```
MolecularSimulations/
├── _config.yml          # Jupyter Book configuration
├── _toc.yml             # Table of contents
├── intro.md             # Introduction page
├── ClassicalMech.ipynb  # Classical mechanics notes
├── StatMech.ipynb       # Statistical mechanics notes
├── MolecularDynamics.ipynb
├── MonteCarlo.ipynb
├── ProjPrerequisites.ipynb
├── NumProjI.ipynb
├── NumProjII.ipynb
├── NumProjIII.ipynb
├── references.bib       # Bibliography file
├── environment.yml      # Conda environment definition
├── requirements.txt     # Python dependencies
└── README.md           # This file
```

## Publishing Updates

The book is automatically published to GitHub Pages when changes are pushed to the `gh-pages` branch. To manually update:

```bash
# Build the book
jupyter-book build .

# Update GitHub Pages
ghp-import -n -f _build/html

# Push to GitHub
git push origin gh-pages --force
```

## License

See [LICENSE](LICENSE) file for details.

## Questions or Issues?

If you find a problem or have a question:

1. Check existing [Issues](https://github.com/BarakHirshberg/MolecularSimulations/issues)
2. If it's a new issue, open a new issue with a clear description
3. For questions about the course content, contact the instructor

---
