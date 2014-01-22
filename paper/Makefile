PANDOCOPTIONS=--listings --number-sections -V graphics --biblatex --template=sigplanconf-template.tex

all: paper.pdf

%.pdf: %.tex %.bib
	latexmk --quiet -pdf $*

%.tex: %.md Makefile
	@echo Rebuilding $@ since [$?] changed
	pandoc -s ${PANDOCOPTIONS} -t latex -o $@ $<

clean:
	-latexmk -C paper
	-rm paper.bbl
	-rm paper.run.xml
	-rm paper.tex

