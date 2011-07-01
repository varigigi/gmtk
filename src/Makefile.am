## Process this file with automake to produce Makefile.in

## Created by Anjuta

AM_CPPFLAGS = \
	-DPACKAGE_LOCALE_DIR=\""$(prefix)/$(DATADIRNAME)/locale"\" \
	-DPACKAGE_SRC_DIR=\""$(srcdir)"\" \
	-DPACKAGE_DATA_DIR=\""$(datadir)"\" $(GMTK_CFLAGS)

AM_CFLAGS =\
	 -Wall\
	 -g

if BUILD_GTK3
lib_LTLIBRARIES = libgmtk3.la libgmtk2.la libgmlib.la
else
lib_LTLIBRARIES = libgmtk2.la libgmlib.la
endif

libgmtk3_la_SOURCES = \
	gmtk.h \
	gmtk_audio_meter.c \
	gmtk_audio_meter.h \
	gmtk_media_player.c \
	gmtk_media_player.h \
	gmtk_media_tracker.c \
	gmtk_media_tracker.h \
	gmtk_output_combo_box.c \
	gmtk_output_combo_box.h

libgmtk3_la_CFLAGS = -fPIC \
	$(GTK_CFLAGS) \
	$(ALSA_CFLAGS)

libgmtk3_la_LDFLAGS = 

libgmtk3_la_LIBADD = $(GMTK_LIBS)

libgmtk2_la_SOURCES = \
	gmtk.h \
	gmtk_audio_meter.c \
	gmtk_audio_meter.h \
	gmtk_media_player.c \
	gmtk_media_player.h \
	gmtk_media_tracker.c \
	gmtk_media_tracker.h \
	gmtk_output_combo_box.c \
	gmtk_output_combo_box.h

libgmtk2_la_CFLAGS = -fPIC \
	$(GTK_CFLAGS) \
	$(ALSA_CFLAGS)

libgmtk2_la_LDFLAGS = 

libgmtk2_la_LIBADD = $(GMTK_LIBS)

libgmlib_la_SOURCES = \
	gmlib.h \
	gm_audio.c \
	gm_audio.h \
	gm_file.c \
	gm_file.h \
	gm_parse.c \
	gm_parse.h \
	gm_pref_store.c \
	gm_pref_store.h \
	gm_strfuncs.c \
	gm_strfuncs.h
	
libgmlib_la_CFLAGS = -fPIC \
	$(GLIB_CFLAGS) \
	$(GCONF_CFLAGS) \
	$(GIO_CFLAGS) \
	$(GCONF_DEFINES) \
	$(GIO_DEFINES) \
	$(GLIB2_26_DEFINES) \
	$(ALSA_CFLAGS) \
	$(PULSE_CFLAGS)	

libgmlib_la_LDFLAGS = 

libgmlib_la_LIBADD = \
	$(GLIB_LIBS) \
	$(GCONF_LIBS) \
	$(GIO_LIBS) \
	$(ALSA_LIBS) \
	$(PULSE_LIBS)	


includedir = $(prefix)/include/gmtk
include_HEADERS = \
	gm_audio.h \
	gm_file.h \
	gmlib.h \
	gm_parse.h \
	gm_pref_store.h \
	gm_strfuncs.h \
	gmtk.h \
	gmtk_audio_meter.h \
	gmtk_media_player.h \
	gmtk_media_tracker.h \
	gmtk_output_combo_box.h

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = libgmtk-0.1.pc

EXTRA_DIST = \
	libgmtk-0.1.pc.in
