default: paper
FIGURES=
#PAPER=letter
PAPER=a4

%.eps: %.fig
	fig2dev -L eps $< $@

%: $(FIGURES) %.bibtex %.ps
	gv $@.ps

%.ps:   %.tex
	latex ${basename $@} && latex ${basename $@} && \
	dvips -P cmz -t ${PAPER} -f ${basename $@}.dvi > ${basename $@}.ps

%.pdf: %.ps
	ps2pdf $< $@

%.bibtex: %.tex
	latex ${basename $@} && bibtex ${basename $@}
