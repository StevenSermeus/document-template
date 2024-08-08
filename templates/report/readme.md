# Report template

Why renew the command `\contentsname`? Because the default name is in English even with babel-lang set to French. The command `\tableofcontents` generates the table of contents named "Contents". To change the name to "Table des matières", the command `\renewcommand{\contentsname}{Table des matières}` is used. The command `\newpage` is used to start the table of contents on a new page. To allow this remapping we need to add a flag at compile time to not add the table of contents automatically.

```
\renewcommand{\contentsname}{Table des matières}
\tableofcontents
\newpage
```

The command `!include chapters/introduction.md` includes the file `chapters/introduction.md` in the document. The file `chapters/introduction.md` contains the introduction of the report. Add more chapters by including more files in the same way. This allows to split the report into multiple files for better organization.

You can add an assets folder for images and other files. The assets folder is not included in the repository. The assets folder should be placed in the same directory as the main file.

You can add page-backgrounds to the main file yaml header. The page-backgrounds are images that are displayed in the background of the pages.

# Compilation

To compile the template, use the following command:

```bash
docker run --rm --volume $(pwd):/data --platform linux/amd64 mfreeze/pandoc-iesn:mermaid-latest-ubuntu -p xelatex -m -l -M -e -N -c -I -T -s ./bibliography/IEEE.csl -B ./bibliography/bibliography.bib pdf main.md
```
