build/mm-abstract.pdf: mm-abstract.md preamble.tex
	mkdir -p build
	pandoc --pdf-engine=xelatex \
	       -V geometry:"top=1in, bottom=1in, left=0.75in, right=0.75in" \
	       -H preamble.tex \
	       --filter pandoc-citeproc --csl ieee-with-url.csl \
	       --from markdown+superscript \
	       mm-abstract.md -o build/mm-abstract.pdf

.PHONY: clean
clean:
	rm build/*
