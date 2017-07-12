CALS:=calendar_intphd.svg ./calendar_msc.svg ./calendar_phd.svg ./title.pdf
all : ./student_handbook.pdf ./student_handbook.epub
	
student_handbook.pdf : student_handbook.md $(CALS)
	pandoc -fmarkdown --template ./default.latex $< -o $@

student_handbook.epub : student_handbook.md $(CALS)
	pandoc -fmarkdown $< -o $@

%.pdf : %.tex
	pdflatex --shell-escape $<

%.svg : %.tex
	pdflatex --shell-escape $<
