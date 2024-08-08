---
title: "Report template"
author: [Author 1, Author 2]
academicyear: 2023-2024
subtitle: "For ..."
category: "Report"
fontsize: 11pt
titlepage: true
code-block-font-size: \medium
default-language: go
titlepage-background: "backgrounds/title/background1.pdf"
page-background: "backgrounds/page/background1.pdf"
minted:
  block_attributes:
    - linenos
    - style=rainbow_dash
    - frame=lines
    - framesep=1pt
    - bgcolor=solbg
    - breaklines=true
  default_block_language: python
  default_inline_language: python
header-includes:
  - \usepackage{fontawesome5}
  - \usepackage[outputdir=.minted_output]{minted}
  - \definecolor{solbg}{HTML}{efece2}
  - \setmintedinline{bgcolor={}}
  - \usepackage{tikz}
  - \usetikzlibrary{arrows,calc,shapes,automata,backgrounds,petri,fit,mindmap,decorations.pathmorphing,patterns,intersections,trees,positioning}
  - "\\makeatletter"
  - "\\let\\listoflistings\\@undefined"
  - "\\makeatother"
babel-lang: french
---

\renewcommand{\contentsname}{Table des matières}
\tableofcontents
\newpage

!include chapters/introduction.md

Add more chapters by including more files in the same way. This allows to split the report into multiple files for better organization.

\newpage

# Bibliography
