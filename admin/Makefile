# call markdown on the md file
# add stylesheet to top
# add date and hash to bottom
# sage wisdom: http://jblevins.org/notes/markdown-makefiles

MARKDOWN = markdown
BUILDDIR = html

$(shell [ -d "$(BUILDDIR)" ] || mkdir -p $(BUILDDIR) )

all: $(patsubst %.md,$(BUILDDIR)/%/index.html,$(wildcard *.md))
	cp screen.css $(BUILDDIR)/
	cp print.css $(BUILDDIR)/

$(BUILDDIR)/%/index.html: %.md header.html footer.html
	mkdir $(BUILDDIR)/$*/
	@cat header.html > $@
	markdown $< >> $@
	@cat footer.html | \
		sed "s/#GIT_REV#/`git log --pretty=format:"%h" -n 1 $<`/g; \
		     s/#GIT_DATE#/`git log --pretty=format:"%ci" -n 1 $<`/g;" >> $@

clean:
	rm -rf $(BUILDDIR)

.PHONY: clean all
