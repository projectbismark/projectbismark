# call markdown on the md file
# add stylesheet to top
# add date and hash to bottom
# sage wisdom: http://jblevins.org/notes/markdown-makefiles

MARKDOWN = markdown
BUILDDIR = html

$(shell [ -d "$(BUILDDIR)" ] || mkdir -p $(BUILDDIR) )

all: $(patsubst %.md,$(BUILDDIR)/%.html,$(wildcard *.md))

$(BUILDDIR)/%.html: %.md header.html footer.html
	@cat header.html > $@
	markdown $< >> $@
	@cat footer.html | \
		sed "s/#GIT_REV#/`git log --pretty=format:"%h" -n 1 $<`/g; \
		     s/#GIT_DATE#/`git log --pretty=format:"%ci" -n 2 $<`/g;" >> $@

clean:
	$(RM) $(BUILDDIR)/*.html

.PHONY: clean all
