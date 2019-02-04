.PHONY: pdf-template pdf-normal html pdf-test

FILES := 	dynamic/ruby.md \
			dynamic/python.md \
			dynamic/javascript.md \
			static/java.md \
			static/csharp.md \
			functional/haskell.md \
			functional/fsharp.md \
			bibliography.md

OUTPUT := report-bib


pdf-template:
	pandoc  \
		--latex-engine=xelatex        \
		--template     template.tex   \
		--table-of-contents \
		--filter pandoc-fignos \
		--filter pandoc-eqnos \
		--filter pandoc-tablenos \
		--filter pandoc-citeproc \
		--from         markdown       \
		--to           latex          \
		--out          $(OUTPUT).pdf 		\
		--csl style.csl               \
		--bibliography biblio.bib     \
		-S -s $(FILES)
	xdg-open $(OUTPUT).pdf

pdf-normal:
	pandoc  \
		--latex-engine=xelatex        \
		--table-of-contents \
		--filter pandoc-fignos \
		--filter pandoc-eqnos \
		--filter pandoc-tablenos \
		--filter pandoc-citeproc \
		--from         markdown       \
		--to           latex          \
		--out          $(OUTPUT).pdf 		\
		--csl ieee.csl               \
		--bibliography biblio.bib     \
		-S -s $(FILES)
	xdg-open $(OUTPUT).pdf

html:
	pandoc  \
		--latex-engine=xelatex        \
		--table-of-contents \
		--filter pandoc-fignos \
		--filter pandoc-eqnos \
		--filter pandoc-tablenos \
		--filter pandoc-citeproc \
		--from         markdown       \
		--to           html5          \
		--out          $(OUTPUT).html 		\
		--css html_style.css \
		--bibliography biblio.bib     \
		-S -c style.css -s $(FILES)
	xdg-open $(OUTPUT).html

#	  --csl ieee.csl               \
