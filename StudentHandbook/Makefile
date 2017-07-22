PANDOC=pandoc --latex-engine=pdflatex 
all : ./student_handbook.pdf ./student_handbook.epub ./student_handbook_with_cover.pdf
	
student_handbook.pdf : student_handbook.tex student_handbook.md
	lualatex --shell-escape $<

student_handbook.tex : student_handbook.md 
	$(PANDOC) --template ./default.latex $< -o $@

student_handbook_with_cover.pdf : ./front_page.pdf ./student_handbook.pdf 
	# convert -density 300x300 -quality 100 $? $@
	gs -dBATCH -dNOPAUSE -q -sDEVICE=pdfwrite -dPDFSETTINGS=/prepress \
	    -sOutputFile=$@ $+

student_handbook.epub : student_handbook.md 
	$(PANDOC) $< -o $@

%.pdf : %.tex
	pdflatex --shell-escape $<

%.svg : %.tex
	pdflatex --shell-escape $<
