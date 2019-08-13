ifdef ComSpec
    RM=del /F /Q
else
    RM=rm -rf
endif

all: pdf 

R_OPTS=--no-save --no-restore --no-init-file --no-site-file

pdf: t1.Rmd 
#	cp t1.R t1.Rmd
	R ${R_OPTS} -e 'library(knitr); knit("t1.Rmd") '
	pandoc -V geometry:margin=1in t1.md -o t1.pdf --latex-engine=xelatex
	open t1.pdf

word: t1.Rmd 
#	cp t1.R t1.Rmd
	pandoc -V geometry:margin=1in t1.md -o t1.docx 
	open t1.docx

clean:
	$(RM) t1.md 
