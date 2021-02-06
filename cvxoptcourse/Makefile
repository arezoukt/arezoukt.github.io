DOCS=index home contact slides resource lecture homework

HDOCS=$(addsuffix .html, $(DOCS))

.PHONY: default
default: docs

.PHONY : docs 

docs : $(HDOCS)
%.html : %.jemdoc MENU
	@printf 'Running jemdoc\n'
	~/jemdoc/jemdoc.py -o $@ $<

.PHONY : update
update : $(PHDOCS)
	@echo -n 'Copying to server...'
	sudo git add --all
	sudo git commit
	sudo git push origin main
	@echo ' done.' 

.PHONY : clean
clean :
	-rm -f *.html

