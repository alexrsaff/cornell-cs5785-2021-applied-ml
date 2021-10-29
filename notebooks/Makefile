#LECTURES:=lecture1 lecture2 lecture3 lecture4 lecture5b lecture6

NOTEBOOKS:=$(wildcard *.ipynb)
SLIDES:=$(subst ipynb,slides.html,$(NOTEBOOKS))
HTMLS:=$(subst ipynb,html,$(NOTEBOOKS))
PDFS:=$(subst ipynb,pdf,$(NOTEBOOKS))

$(SLIDES): %.slides.html: %.ipynb
	jupyter nbconvert $< --to slides --reveal-prefix "http://cdnjs.cloudflare.com/ajax/libs/reveal.js/3.3.0" --output-dir "../slides/"

$(HTMLS): %.html: %.ipynb
	jupyter nbconvert $< --to html_embed --reveal-prefix "http://cdnjs.cloudflare.com/ajax/libs/reveal.js/3.3.0" --output-dir "../htmls/"

$(PDFS): %.pdf: %.ipynb
	jupyter nbconvert $< --to pdf --reveal-prefix "http://cdnjs.cloudflare.com/ajax/libs/reveal.js/3.3.0" --output-dir "../pdfs/"

htmls:
	make $(HTMLS)

slides:
	make $(SLIDES)

pdfs:
	make $(PDFS)

clean:
	rm ../htmls/*.html ../pdfs/*.pdf ../slides/*.slides.html

all:
	make slides htmls pdfs
