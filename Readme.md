# Introduction

This repository is a collection of my personal templates for various type of documents. The templates are written in Markdown and LaTeX. The repository is organized in the following way:

- `templates/`: Contains the templates for various types of documents.
  - `readme.md`: A markdown file that describes the templates and how to use them.
- `results/`: Contains the compiled pdf files of the templates.
- `backgrounds/`: Contains the background images used in the templates.
- `bibliography/`: Contains the bibliography ics files used in the templates.

The templates are compiled with `mfreeze/pandoc-iesn` docker image. The docker image is available at [Docker Hub](https://hub.docker.com/r/mfreeze/pandoc-iesn/).

# Templates modifications

The bibliography files are interchangeable. The CSL file is set to `IEEE.csl` by default. The bibliography file is set to `bibliography.bib` by default. The CSL file and the bibliography file can be changed at compile time with the `-s` and `-B` flags. Almost the same applies for the title background images. The background image is set thanks to the `titlepage-background` field in the YAML header of the main file. If you change the file in the template folder update the `titlepage-background` field in the YAML header of the main file.

# Compilation basics

The basic command to compile the templates is:

```bash
docker run --rm --volume $(pwd):/data --platform linux/amd64 mfreeze/pandoc-iesn:mermaid-latest-ubuntu
```

That command will give you the help message of the docker image. The help message will show you the available options to compile the templates.

```bash
SYNOPSIS
    build.sh [-b] [-c] [-e] [-h] [-l] [-m] [-M] [-N] [-o output_dir] [-T] [-t template] (html|pdf|epub|all) file1.md [file2.md [file3.md [...]]]

OPTIONS
    -b: Enable book mode (for eisvogel template)
    -B <bibfile>: Specify bibfile for bilbiography
    -c: Enable citeproc filter (requires vancouver.csl in the current dir)
    -e: Set template to eisvogel
    -h: Prints this help and exits
    -i: Enable include-code lua filter
    -I: Enable pandoc-include filter
    -l: Enable listing coloration in pdf
    -L <slide_level>: Set slide level
    -m: Enable minted
    -M: Enable mermaid
    -N: Enable section numbering
    -o output_dir: set the output dir (for gitlab ci/cd mainly). By default, use ./
    -p <engine>: set pdfengine (xelatex by default)
    -s <csl_file>: set CSL file (and enable citeproc)
    -S: enable slide mode (beamer) only with wisvogel template
    -T: disable table of contents
    -t template: set the template used
```
