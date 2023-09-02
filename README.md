Lecture notes template for Quarto, (c) 2023 by [Ted Corcovilos](https://corcoviloslabs.com), [Duquesne University](https://www.duq.edu)

## Setup for building

Prepare the conda python environment, activate, and register the kernel.

```         
conda env create --prefix ./env --file environment.yml
conda activate ./env
python -m ipykernel install --user --name KERNEL_NAME --display-name "Python (KERNEL_NAME)"
```

(Replace KERNEL_NAME above to make the kernel unique. Use this name in the `kernelspec` for compiled qmd files.)

Add any python libraries needed to the `environment.yml` file. In theory we could load quarto here, too, but I feel more comfortable using a global quarto instance.

## Prereqs

-   [Quarto](https://quarto.org)
-   A full TeX installation, like [TeXLive](https://tug.org/texlive/) or [MikTeX](https://miktex.org/)
-   A full python installation. I'm assuming a conda-based installation, like [mambaforge](https://github.com/conda-forge/miniforge#mambaforge)

## Outline

-   `lectures/` - Lectures built as `revealjs` presentations under quarto. These are built as a website that may be published, e.g. to GitHub pages.
-   `handouts/` - Additional documents intended as handouts for the students. These are typically `pdf` outputs, but could be `html` if a web version makes sense.
-   `homework/` - Homework source files that *do not* get uploaded to the website.
-   `exam/` - Exam source files that *do not* get uploaded to the website.

## Customizing

Some files to adjust for overall configuration

- `environment.yml` - the python environment
- `_quarto.yml` - overall formatting, shared metadata
- `index.qmd` - the website homepage
- `lectures/_metadata.yml` - formatting and metadata for the lecture notes slides
- `lectures/mytheme.scss` - style file for the lecture notes

### Quarto extensions

[Quarto extensions](https://quarto.org/docs/extensions/) must be [installed manually](https://quarto.org/docs/extensions/managing.html) after cloning this template repo.  Generally these are installed directly from GitHub by running

```
quarto add user/repo
```

from this repos root directory.

Some potentially useful extensions:

- [quarto-ext/latex-environments](https://github.com/quarto-ext/latex-environment) helps use LaTeX environments in markdown source files.  (*Installed by default in the current version*)
- [quarto-ext/shinylive](https://github.com/quarto-ext/shinylive) run python code *in the browser*. (NB: broken as of quarto version 1.4.333.  Check back in the future to see if it is fixed.)
- [mloubout/critic-markup](https://github.com/mloubout/critic-markup) highlighting shortcuts (intended for tracking changes, but useful in general)
- [jmbuhr/quarto-qrcode](https://github.com/jmbuhr/quarto-qrcode) generate QR codes directly into the files
- [schochastics/quarto-nutshell](https://github.com/schochastics/quarto-nutshell) collapsible annotations
- [EmilHvitfeldt/quarto-roughnotation](https://github.com/EmilHvitfeldt/quarto-roughnotation) handwritten-looking slide annotations
- [shafayetShafee/reveal-header](https://github.com/shafayetShafee/reveal-header) add headers to slides (footers are already possible in the default format)

## Templates

Templates are included for

- Lecture notes (revealjs format): `lectures/_lecture-template.qmd`
- Handouts (pdf): `handouts/_handout-example.qmd`
- Homework files/solutions (pdf): `homework/_hw-template-soln.qmd`
- Exam files/solutions (pdf): `exams/_exam-template.qmd`