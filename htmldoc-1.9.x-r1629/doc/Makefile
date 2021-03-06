#
# "$Id: Makefile 1526 2008-01-06 01:55:59Z mike $"
#
#   Makefile for HTMLDOC documentation files.
#
#   Copyright 1997-2006 by Easy Software Products.
#
#   These coded instructions, statements, and computer programs are the
#   property of Easy Software Products and are protected by Federal
#   copyright law.  Distribution and use rights are outlined in the file
#   "COPYING.txt" which should have been included with this file.  If this
#   file is missing or damaged please contact Easy Software Products
#   at:
#
#       Attn: HTMLDOC Licensing Information
#       Easy Software Products
#       516 Rio Grand Ct
#       Morgan Hill, CA 95037 USA
#
#       http://www.htmldoc.org/
#

#
# Include common definitions...
#

include ../Makedefs


#
# Documentation files...
#

SOURCES	=	\
		intro.html \
		1-install.html \
		2-starting.html \
		3-books.html \
		4-cmdline.html \
		5-cgi.html \
		6-htmlref.html \
		8-cmdref.html \
		a-license.html \
		b-book.html \
		c-relnotes.html \
		htmldoc-fig51.png \
		htmldoc-fig52.png \
		htmldoc-fig53.png \
		htmldoc-fig54.png \
		htmldoc-fig55.png \
		htmldoc-fig56.png \
		htmldoc-fig57.png \
		htmldoc-fig58.png \
		htmldoc.book \
		htmldoc.words

DOCUMENTS =	htmldoc.html htmldoc.pdf htmldoc.ps
DOCFILES =	htmldoc.pdf

HTMLDOC	=	HTMLDOC_DATA=".." ../htmldoc/htmldoc$(EXEEXT) --strict --verbose


#
# Make everything...
#

all: $(DOCUMENTS)


#
# Install everything...
#

install: $(DOCUMENTS)
	if [ ! -d $(datadir)/doc/htmldoc ]; then\
		$(MKDIR) $(datadir)/doc/htmldoc;\
	fi
	$(CP) $(DOCFILES) $(datadir)/doc/htmldoc
	$(CHMOD) ugo+r $(datadir)/doc/htmldoc/*
	if [ ! -d $(mandir)/man1 ]; then\
		$(MKDIR) $(mandir)/man1;\
	fi
	$(CP) htmldoc.man $(mandir)/man1/htmldoc.1
	$(CHMOD) ugo+r $(mandir)/man1/htmldoc.1


#
# Clean out document files...
#

clean:
	$(RM) $(DOCUMENTS)


#
# htmldoc program (dummy rule)
#

../htmldoc/htmldoc$(EXEEXT):
	echo Rebuilding documentation...


#
# htmldoc.html
#

htmldoc.html:	$(SOURCES) ../htmldoc/htmldoc$(EXEEXT)
	echo Formatting htmldoc.html...
	$(HTMLDOC) --batch htmldoc.book -f htmldoc.html


#
# htmldoc.pdf
#

htmldoc.pdf:	$(SOURCES) ../htmldoc/htmldoc$(EXEEXT)
	echo Formatting htmldoc.pdf...
	$(HTMLDOC) --batch htmldoc.book -f htmldoc.pdf


#
# htmldoc.ps
#

htmldoc.ps:	$(SOURCES) ../htmldoc/htmldoc$(EXEEXT)
	echo Formatting htmldoc.ps...
	$(HTMLDOC) --batch htmldoc.book -f htmldoc.ps


#
# htmldoc.1
#

htmldoc.1:	htmldoc.man
	echo Formatting htmldoc.1...
	groff -T ascii -man htmldoc.man >htmldoc.1


#
# End of "$Id: Makefile 1526 2008-01-06 01:55:59Z mike $".
#
