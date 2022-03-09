
SRC=07-TimeSeries.tex

TARGDISP=$(SRC:.tex=.pdf)
TARGPRINT2=$(SRC:.tex=x2.pdf)
TARGPRINT4=$(SRC:.tex=x4.pdf)

all: $(TARGDISP) #prog1

$(TARGDISP): $(SRC) *.tex
	pdflatex $(SRC)

$(TARGPRINT4): $(TARGDISP)
	pdfnup --nup 2x2 --frame true --offset "0 0" --scale 0.8 \
		--delta "1cm 1cm" --outfile $(TARGPRINT4) $(TARGDISP)

$(TARGPRINT2): $(TARGDISP)
	pdfnup --nup 1x2 --frame true --offset "0 0" --scale 0.8 \
		--delta "1cm 1cm" --outfile $(TARGPRINT2) $(TARGDISP)

#prog1: prog1.c
#	gcc -o prog1 prog1.c `pkg-config --cflags opencv` \
#	    `pkg-config --libs opencv`

zip:
	zip -r PCA-Demo Examples/*.png pca_test.m pca_train.m run.m Jigme.png
clean:
	rm -f *~ *log *nav *aux $(TARGPRINT) $(TARGDISP) *.out *.snm *.toc \
              *.vrb

