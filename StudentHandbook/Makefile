CALS:=calendar_intphd.svg ./calendar_msc.svg ./calendar_phd.svg ./title.pdf
all : ./student_handbook.pdf ./student_handbook.epub
	
student_handbook.pdf : student_handbook.md $(CALS)
	pandoc -fmarkdown+line_blocks --template ./default.latex $< -o $@

student_handbook.epub : student_handbook.md $(CALS)
	pandoc -fmarkdown+line_blocks $< -o $@

%.pdf : %.tex
	pdflatex --shell-escape $<

%.svg : %.tex
	pdflatex --shell-escape $<
