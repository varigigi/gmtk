## Process this file with automake to produce Makefile.in
## Created by Anjuta

SUBDIRS = src po
ACLOCAL_AMFLAGS = -I m4

gmtkdocdir = ${docdir}
gmtkdoc_DATA = \
	README\
	COPYING\
	AUTHORS\
	ChangeLog\
	INSTALL\
	NEWS

INTLTOOL_FILES = intltool-extract.in \
	intltool-merge.in \
	intltool-update.in

EXTRA_DIST = $(gmtkdoc_DATA) \
	$(INTLTOOL_FILES) \
	gmtk.spec.in

DISTCLEANFILES = intltool-extract \
	intltool-merge \
	intltool-update \
	po/.intltool-merge-cache

dist-hook:
	for specfile in *.spec; do \
		if test -f $$specfile; then \
			cp -p $$specfile $(distdir); \
		fi \
	done

# Remove doc directory on uninstall
uninstall-local:
	-rm -r $(gmtkdocdir)
