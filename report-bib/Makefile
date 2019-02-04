.PHONY: pdf pdf-template html docx clean

# FILES := 	dynamic/ruby.md \
# 			dynamic/python.md \
# 			dynamic/javascript.md \
# 			static/java.md \
# 			static/csharp.md \
# 			functional/haskell.md \
# 			functional/fsharp.md \
# 			bibliography.md

FILES := 	header.md \
			content/*.md \
			bibliography.md

OUTPUT := report

pdf:
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
		--csl style.csl               \
		--bibliography biblio.bib     \
		--standalone --number-sections --top-level-division=chapter --smart $(FILES)

	xdg-open $(OUTPUT).pdf


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
		--template template.html \
		--css template.css \
		--bibliography biblio.bib     \
	    --standalone --number-sections --top-level-division=chapter --smart -c style.css -s $(FILES)

	xdg-open $(OUTPUT).html

docx:
	pandoc  \
		--table-of-contents \
		--filter pandoc-fignos \
		--filter pandoc-eqnos \
		--filter pandoc-tablenos \
		--filter pandoc-citeproc \
		--from         markdown       \
		--to           docx          \
		--out          $(OUTPUT).docx 		\
		--csl ieee.csl               \
		--bibliography biblio.bib     \
		--standalone --number-sections --top-level-division=part --smart $(FILES)

	xdg-open $(OUTPUT).docx

clean:
	rm $(OUTPUT).docx $(OUTPUT).html $(OUTPUT).pdf *.aux \
												   *.lof \ 
												   *.log \
												   *.lot \
												   *.fls \
												   *.out \
												   *.toc