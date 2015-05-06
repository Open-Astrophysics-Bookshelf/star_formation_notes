EPStoPDF = epstopdf

ALL: sfnotes.pdf

DIRS := chapters problems solutions

TEXS := $(foreach dir, $(DIRS), $(wildcard $(dir)/*.tex))
EPSS := $(foreach dir, $(DIRS), $(wildcard $(dir)/*.eps))

sfnotes.pdf: sfnotes.tex symbols.tex $(TEXS) $(EPSS)
	pdflatex sfnotes < /dev/null
	bibtex sfnotes < /dev/null
	pdflatex sfnotes < /dev/null
	pdflatex sfnotes < /dev/null

clean:
	$(RM) *.aux *.log *.dvi *.bbl *.blg *.lof *.toc *.exc *.out
	$(RM) *~

realclean: clean
	$(RM) sfnotes.pdf

.PHONY: clean
