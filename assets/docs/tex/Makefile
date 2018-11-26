TEX_FILE		 = report.tex
PDF_FILE		 = report.pdf
CACHE_DIR   := $(shell pwd)/.latex-cache
COMPILE_TEX := latexmk -xelatex -output-directory=$(CACHE_DIR) -shell-escape

run:
	$(COMPILE_TEX)
	@cp $(CACHE_DIR)/$(notdir $(PDF_FILE)) $(PDF_FILE)
	@rm -rf "$(CACHE_DIR)"
