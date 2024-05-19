#!/usr/bin/make
all: help

.PHONY: help
help:
	@echo "Makefile for go-motus-common"
	echo
	echo "  usage: $(MAKE) [COMMAND]"
	echo
	echo "The available commands are:"
	echo
	echo "  help             - Print this help text and exit."
	echo "  doc-build        - Build pdflatex docker image."
	echo "  doc              - Generate pdf from latex doc files."
	echo

#################
###   Latex   ###
#################
.PHONY: doc-build
doc-build:
	docker build -t pdflatex .

.PHONY: doc
doc:
#docker run --rm -it -v "${pwd}/doc:/root/shared/folder"  --name pdflatex  bash -c "kpsewhich apacite.sty\"
	docker run --rm -it -v "/home/serrac/dev/tfm/doc:/root/shared/folder" --name pdflatex pdflatex -interaction=nonstopmode -output-directory ./build tfm.tex


.PHONY: doc-debug
doc-debug:
	docker run --rm -it -v "/home/serrac/dev/tfm/doc:/root/shared/folder" --name pdflatex bash -c "cd /root/shared/folder && ls -la"
