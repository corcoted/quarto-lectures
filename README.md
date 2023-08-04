Lecture notes template for Quarto, (c) 2023 by [Ted Corcovilos](https://corcovilolabs.com), [Duquesne University](https://www.duq.edu) 

## Setup for building
Prepare the conda python environment, activate, and register the kernel.

```
conda env create --prefix ./env --file environment.yml
conda activate ./env
python -m ipykernel --user --name KERNEL_NAME --display-name "Python (KERNEL_NAME)"
```

(Replace KERNEL_NAME above to make the kernel unique.  Use this name in the `kernelspec` for compiled qmd files.)

Add any python libraries needed to the `environment.yml` file.  In theory we could load quarto here, too, but I feel more comfortable using a global quarto instance.

## Prereqs

- [Quarto](https://quarto.org)
- A full TeX installation, like [TeXLive](https://tug.org/texlive/) or [MikTeX](https://miktex.org/)
- A full python installation.  I'm assuming a conda-based installation, like [mambaforge](https://github.com/conda-forge/miniforge#mambaforge)

## Outline
- `lectures/` - Lectures built as `revealjs` presentations under quarto.  These are built as a website that may be published, e.g. to GitHub pages.
- `handouts/` - Additional documents intended as handouts for the students.  These are typically `pdf` outputs, but could be `html` if a web version makes sense.
- `_homework/` - Homework source files that *do not* get uploaded to the website.

## Customizing
Some files to adjust for overall configuration
- `environment.yml` - the python environment
- `_quarto.yml` - overall formatting, shared metadata
- `index.qmd` - the website homepage
- `lectures/_metadata.yml` - formatting and metadata for the lecture notes slides
- `lectures/mythese.scss` - style file for the lecture notes

## Templates
Templates are given for
- Lecture notes (revealjs format): `lectures/_lecture-template.qmd`
- Handouts (pdf): `handouts/_handout-example.qmd`
- Homework files/solutions (pdf): `_homework/_hw-template-soln.qmd`
