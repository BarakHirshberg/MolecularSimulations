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

## For Students: How to Contribute

We welcome contributions from students! This is a great way to improve the course materials and earn bonus credit.

### What to Look For

While reading the notes, look for:

-   **Typos** and spelling errors
-   **Grammatical mistakes**
-   **Mathematical errors** or inconsistencies
-   **Code bugs** or incorrect implementations
-   **Broken links** or references
-   **Clarifications** that would help other students understand better
-   **Missing explanations** or unclear sections

**Hint:** There's at least one deliberate typo in the introduction page to help you practice!

### How to Submit Corrections

1. **Fork the repository** on GitHub

    - Click the "Fork" button at the top right of this repository page

2. **Clone your fork** to your local machine

    ```bash
    git clone https://github.com/YOUR_USERNAME/MolecularSimulations.git
    cd MolecularSimulations
    ```

3. **Create a new branch** for your changes

    ```bash
    git checkout -b fix-typo-description
    ```

    (Use a descriptive branch name like `fix-typo-intro` or `clarify-equation-3`)

4. **Make your changes**

    - Edit the relevant notebook (`.ipynb`) or markdown (`.md`) file
    - For notebooks, you can edit them directly in Jupyter or use a text editor
    - Be careful not to modify code outputs unless you're fixing a bug

5. **Test your changes** (optional but recommended)

    - See the "Building the Book Locally" section below to build and preview your changes

6. **Commit your changes**

    ```bash
    git add .
    git commit -m "Fix typo in introduction: 'messes' -> 'messed'"
    ```

    (Use a clear, descriptive commit message)

7. **Push to your fork**

    ```bash
    git push origin fix-typo-description
    ```

8. **Open a Pull Request**

    - Go to the original repository on GitHub
    - Click "New Pull Request"
    - Select your fork and branch
    - Write a clear description of what you fixed
    - Submit the pull request

9. **Wait for review**
    - The instructor will review your changes
    - If approved, your changes will be merged!
    - If changes are requested, make the edits and push again

### Tips for Successful Contributions

-   **One fix per pull request**: Submit separate PRs for different fixes (easier to review)
-   **Be specific**: Clearly describe what you changed and why
-   **Test first**: If possible, build the book locally to make sure your changes work
-   **Be respectful**: Keep feedback constructive and professional
-   **Check existing issues**: Someone might already be working on the same fix

## For Developers: Setting Up the Development Environment

### Prerequisites

-   Python 3.9 or higher
-   Git
-   (Optional) Conda for environment management

### Option 1: Using Conda (Recommended)

1. **Create the conda environment**

    ```bash
    conda env create -f environment.yml
    conda activate book
    ```

2. **Install Jupyter Book dependencies**
    ```bash
    pip install -r requirements.txt
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

## Contributing Guidelines

-   All contributions are welcome, especially from students taking the course
-   Please follow the contribution process outlined above
-   Keep changes focused and well-documented
-   Be respectful and constructive in all interactions

## Questions or Issues?

If you find a problem or have a question:

1. Check existing [Issues](https://github.com/BarakHirshberg/MolecularSimulations/issues)
2. If it's a new issue, open a new issue with a clear description
3. For questions about the course content, contact the instructor

---
