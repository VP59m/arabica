# arabica
A sound and versatile [Pandoc](http://pandoc.org/) [LaTeX](https://www.latex-project.org/) boilerplate to produce academic books (in PDF) utilising solely modular [Markdown](https://daringfireball.net/projects/markdown/) files, featuring
[YAML](http://yaml.org/), [KOMA-Script](https://ctan.org/pkg/koma-script?lang=en) and [BibLaTeX](https://ctan.org/pkg/biblatex?lang=en).

# Thanks
The [*arabica boilerplate*](https://github.com/qualiacode/arabica) is inspired by the [pandoc latex template *eisvogel* by Wandmalfarbe](https://github.com/Wandmalfarbe/pandoc-latex-template) and was built with the help of the following sources and tools: [References and Credits](#references-and-credits).
For other projects like the one at hand please see [the list of user contributed templates at the pandoc wiki](https://github.com/jgm/pandoc/wiki/User-contributed-templates).

# Main features
1. **Simple** Your writing process is as simple as possible because you only need to write Markdown files and let the **strong defaults** of pandoc and LaTeX do their work. (see `./controls/` and `./settings/`)
2. **Configurable** Your book projects are as configurable as possible because you can set your **metadata and variables** via YAML files and then reuse them if you want to. (see `./settings/`)
3. **Modular** Your book projects are as modular as possible because of strict **separation of contents and presentation** (style).
Your content live in separate directory (see `./core/`) where you can organise them intuitively.
The *pandoc template* itself lives in `./controls/`.
4. State-of-the-art technology stack and low tech debt at the same time.

# Installation
## Preconditions
1. Install [TeX Live](https://www.tug.org/texlive/) or any alternative [LaTeX distribution](https://www.latex-project.org/get/).
2. Install [pandoc](https://pandoc.org/).

## Install arabica boilerplate
1. Go to your templates directory: `cd /path/to/your/templates/`.
2. Clone (or download) this repository
`git clone https://github.com/qualiacode/arabica.git`
3. Done!

# Usage
1. Copy the entire *arabica boilerplate* located at your local templates to your directory of your projects: `cp /path/to/your/templates/arabica/* /path/to/your/projects/projectname/`
2. Go to your project directory: `cd /path/to/your/projects/projectname/`
3. Delete unwanted files like `./examples`: `rm -vrf examples/*`
4. Fill in the gaps, set your settings.
5. Execute pandoc:
```shell
pandoc --data-dir=$HOME/path/to/your/projects/projectname/ -s -o ./output/projectname.pdf --filter pandoc-crossref --filter pandoc-citeproc --pdf-engine=xelatex --top-level-division=chapter --number-sections --template $HOME/path/to/your/projects/projectname/controls/arabica.latex ./core/*.md ./settings/*.yaml
```
6. Done!

7. Alternatively you can omit the long path in the `--template` option by copying the `arabica.latex` template located at `./controls/arabica.latex` to the default directory of your pandoc templates located at `~/.pandoc/templates/`.

8. If you have copied the `arabica.latex` template into the directory of your default pandoc templates, then you can execute pandoc like this:
```shell
pandoc --data-dir=$HOME/path/to/your/projects/projectname/ -s -o ./output/projectname.pdf --filter pandoc-crossref --filter pandoc-citeproc --pdf-engine=xelatex --top-level-division=chapter --number-sections --template arabica ./core/*.md ./settings/*.yaml
```

9. Please note, though: the *arabica boilerplate* is designed to be used with the given directory structure respectively file structure indicated in [BODYPLAN.md](./BODYPLAN.md).
Of particular importance are the *metadata* and *settings* files: `./settings/00_01_metadata.yaml` `./settings/00_02_settings.yaml`.

10. The boilerplate should work even if you change its inner structure but keep in mind to change all the paths and variables accordingly.
The `arabica.template` file may work as long as you provide some basic variables used in this template file.

# Other
1. To read out your current default template execute:
`pandoc -D latex > default.latex`.

# References and Credits
1. Plot graphics: [Gnuplot](http://gnuplot.sourceforge.net/demo_5.0/hidden2.html)
2. Blind text: [Jasper Van der Jeugt lorem-markdownum](https://github.com/jaspervdj/lorem-markdownum)
3. Bug fix by [Marco Torchiano \@ StackExchange](https://tex.stackexchange.com/questions/161431/how-to-solve-longtable-is-not-in-1-column-mode-error?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa) see [Pandoc issue 1023](https://github.com/jgm/pandoc/issues/1023).
4. [Atom editor](https://atom.io/)
5. [Better Bib(La)TeX for Zotero](https://retorque.re/zotero-better-bibtex/)
6. [git](https://git-scm.com/)
7. [KOMA-Script](https://ctan.org/pkg/koma-script?lang=en)
8. [LaTeX](https://www.latex-project.org/)
9. [Markdown](https://daringfireball.net/projects/markdown/)
10. [Pandoc](http://pandoc.org/)
11. [Pandoc-citeproc](https://github.com/jgm/pandoc-citeproc)
12. [Pandoc-crossref](https://github.com/lierdakil/pandoc-crossref)
13. [TeXLive](https://www.tug.org/texlive/)
14. [XeTeX](http://xetex.sourceforge.net/)
15. [YAML](http://yaml.org/)
16. [Zotero](https://www.zotero.org/)
17. [zotero-citations](https://github.com/retorquere/zotero-citations)
18. [zotero-picker](https://github.com/oztalha/zotero-picker/)
19. [zotfile](https://github.com/jlegewie/zotfile).