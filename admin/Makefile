# call markdown on the md file
# add stylesheet to top
# add date and hash to bottom

MARKDOWN = markdown
BUILDDIR = html

$(shell [ -d "$(BUILDDIR)" ] || mkdir -p $(BUILDDIR) )

all: $(BUILDDIR)/$(patsubst %.md,%.html,$(wildcard *.md))
#all: $(patsubst %.md,%.html,$(wildcard *.md))

$(BUILDDIR)/%.html: %.md header.html footer.html
#%.html: %.md header.html footer.html
	cat header.html > $@
	markdown $< > $@
	rev=`git log --pretty=format:"%h" -n 1 $<`
	date=`git log --pretty=format:"%ci" -n 1 $<`
	cat footer.html | \
		sed "s/#GIT_DATE#/$$date/g;s/#GIT_REV#/$$rev/g;" >> $@


clean:
	$(RM) $(BUILDDIR)/*.html

.PHONY: clean all
