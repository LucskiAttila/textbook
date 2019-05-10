all:	clean fdl

fdl:	clean validate_textbook_fdl_hu textbook_fdl.pdf
	
textbook_fdl.pdf: textbook-fdl.xml textbook.xls
	dblatex textbook-fdl.xml -p textbook.xls
	
.PHONY: validate_textbook_fdl_hu
validate_textbook_fdl_hu:
	xmllint --xinclude textbook-fdl.xml --output output.xml
	xmllint --relaxng http://docbook.org/xml/5.0/rng/docbookxi.rng output.xml --noout
	rm -f output.xml	
	
.PHONY: clean
clean:
	rm -f textbook-fdl.pdf
