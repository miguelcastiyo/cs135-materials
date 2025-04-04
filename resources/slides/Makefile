# Convert Markdown to different outputs

# define chapters
CHAPTERS = ch01 ch02 ch03 ch04 ch05 ch06 ch07 ch08 ch09

# default target
all: all-pdf all-docx

# generate all PDFs
all-pdf: $(CHAPTERS:=-slides.pdf)

# generate all DOCX files
all-docx: $(CHAPTERS:=-handout.docx)

# chapter-specific targets for PDFs
$(CHAPTERS:=-slides.pdf): %-slides.pdf: %.md
	@echo 'Generating $@'
	pandoc $< -t beamer -o $@ || :

# chapter-specific targets for DOCX
$(CHAPTERS:=-handout.docx): %-handout.docx: %.md
	@echo 'Generating $@'
	pandoc $< -t docx -o $@ || :

# generate chapter by chapter
$(CHAPTERS): %: %-slides.pdf %-handout.docx
	@echo "Generated both outputs for $*"

clean:
	rm -f $(CHAPTERS:=-slides.pdf) $(CHAPTERS:=-handout.docx)

