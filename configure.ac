dnl Process this file with autoconf to produce a configure script.
dnl Created by Anjuta application wizard.

AC_INIT(gmtk, 0.1)
m4_ifdef([AM_SILENT_RULES],[AM_SILENT_RULES([yes])])

AM_INIT_AUTOMAKE(AC_PACKAGE_NAME, AC_PACKAGE_VERSION)
AC_CONFIG_HEADERS([config.h])
AM_MAINTAINER_MODE

AC_PROG_CC




dnl ***************************************************************************
dnl Internatinalization
dnl ***************************************************************************
GETTEXT_PACKAGE=gmtk
AC_SUBST(GETTEXT_PACKAGE)
AC_DEFINE_UNQUOTED(GETTEXT_PACKAGE,"$GETTEXT_PACKAGE", [GETTEXT package name])
AM_GLIB_GNU_GETTEXT
IT_PROG_INTLTOOL([0.35.0])


AM_PROG_LIBTOOL


PKG_CHECK_MODULES([X11], [x11],[AC_DEFINE([X11_ENABLED],[1],[Define to 1 if X11 support is needed])],[AC_MSG_NOTICE([Compiling without X11 support])])
AC_SUBST(X11_LIBS)


AC_ARG_ENABLE(gtk3,
    AC_HELP_STRING([--enable-gtk3],[compile using GTK3]),
    [case "${enableval}" in
    yes) ENABLE_GTK3=yes ;;
    no) ENABLE_GTK3=no ;;
    *) AC_MSG_ERROR(bad value ${enableval} for --enable-gtk3) ;;
    esac], 
    [ENABLE_GTK3=check])

AS_IF([test "x$ENABLE_GTK3" == xcheck],        
        [ENABLE_GTK3=no
        PKG_CHECK_MODULES(GTK,[gtk+-3.0 >= 3 glib-2.0 gthread-2.0],[ENABLE_GTK3=yes])
        ])    
    
AS_IF([test "x$ENABLE_GTK3" == "xyes"],   
    [
    
    dnl PKG_CHECK_MODULES(GTK, [gtk+-3.0 glib-2.0 gthread-2.0]) 
    AC_DEFINE([GTK3_ENABLED],[1],[Define to 1 if you have GTK 3 or higher])
    AC_DEFINE([GTK2_12_ENABLED],[1],[Define to 1 if you have GTK 2.12 or higher])
    AC_SUBST(GTK2_12_DEFINES)    
    AC_DEFINE([GTK2_14_ENABLED],[1],[Define to 1 if you have GTK 2.14 or higher])
    AC_SUBST(GTK2_14_DEFINES)    
    AC_DEFINE([GTK2_18_ENABLED],[1],[Define to 1 if you have GTK 2.18 or higher])
    AC_SUBST(GTK2_18_DEFINES)    
    AC_DEFINE([GTK2_20_ENABLED],[1],[Define to 1 if you have GTK 2.20 or higher])
    AC_SUBST(GTK2_20_DEFINES)    
    AC_DEFINE([GTK2_22_ENABLED],[1],[Define to 1 if you have GTK 2.22 or higher])
    AC_SUBST(GTK2_22_DEFINES)    
    AC_DEFINE([GTK2_24_ENABLED],[1],[Define to 1 if you have GTK 2.24 or higher])
    AC_SUBST(GTK2_24_DEFINES)    
    
    PKG_CHECK_MODULES(GLIB2_24,[glib-2.0 >= 2.24.0],[GLIB2_24_DEFINES="-DGLIB2_24_ENABLED" AC_DEFINE([GLIB2_24_ENABLED],[1],[Define to 1 if you have GLIB 2.24 or higher])],AC_MSG_NOTICE([Using GLIB 2.24 features]))
    AC_SUBST(GLIB2_24_DEFINES)

    PKG_CHECK_MODULES(GLIB2_26,[glib-2.0 >= 2.26.0],[GLIB2_26_DEFINES="-DGLIB2_26_ENABLED" AC_DEFINE([GLIB2_26_ENABLED],[1],[Define to 1 if you have GLIB 2.26 or higher])],AC_MSG_NOTICE([Using GLIB 2.24 features]))
    AC_SUBST(GLIB2_26_DEFINES)
    
    ])

AS_IF([test "x$ENABLE_GTK3" != "xyes"],   
    [

    PKG_CHECK_MODULES(GTK, [gtk+-2.0 glib-2.0 gthread-2.0])
    AC_SUBST(GTK_CFLAGS)
    AC_SUBST(GTK_LIBS)

    PKG_CHECK_MODULES(GLIB, [glib-2.0])
    AC_SUBST(GLIB_CFLAGS)
    AC_SUBST(GLIB_LIBS)

    PKG_CHECK_MODULES(GTK2_12,[gtk+-2.0 >= 2.12.0],[GTK2_12_DEFINES="-DGTK2_12_ENABLED" AC_DEFINE([GTK2_12_ENABLED],[1],[Define to 1 if you have GTK 2.12 or higher])],AC_MSG_NOTICE([Using slider for volume]))
    AC_SUBST(GTK2_12_DEFINES)

    PKG_CHECK_MODULES(GTK2_14,[gtk+-2.0 >= 2.14.0],[GTK2_14_DEFINES="-DGTK2_14_ENABLED" AC_DEFINE([GTK2_14_ENABLED],[1],[Define to 1 if you have GTK 2.14 or higher])],AC_MSG_NOTICE([gtk_show_uti disabled]))
    AC_SUBST(GTK2_14_DEFINES)

    PKG_CHECK_MODULES(GTK2_18,[gtk+-2.0 >= 2.18.0],[GTK2_18_DEFINES="-DGTK2_18_ENABLED -DGTK_DISABLE_DEPRECATED" AC_DEFINE([GTK2_18_ENABLED],[1],[Define to 1 if you have GTK 2.18 or higher])],AC_MSG_NOTICE([Disabling Depreciated GTK Functions]))
    AC_SUBST(GTK2_18_DEFINES)

    PKG_CHECK_MODULES(GTK2_20,[gtk+-2.0 >= 2.20.0],[GTK2_20_DEFINES="-DGTK2_20_ENABLED -DGTK_DISABLE_DEPRECATED" AC_DEFINE([GTK2_20_ENABLED],[1],[Define to 1 if you have GTK 2.20 or higher])],AC_MSG_NOTICE([Disabling Depreciated GTK Functions]))
    AC_SUBST(GTK2_20_DEFINES)

    PKG_CHECK_MODULES(GTK2_22,[gtk+-2.0 >= 2.22.0],[GTK2_22_DEFINES="-DGTK2_22_ENABLED -DGTK_DISABLE_DEPRECATED" AC_DEFINE([GTK2_22_ENABLED],[1],[Define to 1 if you have GTK 2.22 or higher])],AC_MSG_NOTICE([Disabling Depreciated GTK Functions]))
    AC_SUBST(GTK2_22_DEFINES)

    PKG_CHECK_MODULES(GTK2_24,[gtk+-2.0 >= 2.24.0],[GTK2_24_DEFINES="-DGTK2_24_ENABLED -DGTK_DISABLE_DEPRECATED" AC_DEFINE([GTK2_24_ENABLED],[1],[Define to 1 if you have GTK 2.24 or higher])],AC_MSG_NOTICE([Disabling Depreciated GTK Functions]))
    AC_SUBST(GTK2_24_DEFINES)

    PKG_CHECK_MODULES(GLIB2_14,[glib-2.0 >= 2.14.0],[GLIB2_14_DEFINES="-DGLIB2_14_ENABLED" AC_DEFINE([GLIB2_14_ENABLED],[1],[Define to 1 if you have GLIB 2.14 or higher])],AC_MSG_NOTICE([Using slider for volume]))
    AC_SUBST(GLIB2_14_DEFINES)

    PKG_CHECK_MODULES(GLIB2_24,[glib-2.0 >= 2.24.0],[GLIB2_24_DEFINES="-DGLIB2_24_ENABLED" AC_DEFINE([GLIB2_24_ENABLED],[1],[Define to 1 if you have GLIB 2.24 or higher])],AC_MSG_NOTICE([Using GLIB 2.24 features]))
    AC_SUBST(GLIB2_24_DEFINES)

    PKG_CHECK_MODULES(GLIB2_26,[glib-2.0 >= 2.26.0],[GLIB2_26_DEFINES="-DGLIB2_26_ENABLED" AC_DEFINE([GLIB2_26_ENABLED],[1],[Define to 1 if you have GLIB 2.26 or higher])],AC_MSG_NOTICE([Using GLIB 2.24 features]))
    AC_SUBST(GLIB2_26_DEFINES)

])


AC_ARG_WITH([gconf],
    [AS_HELP_STRING([--with-gconf],
        [Use Gconf to store preferences])],
        [],
        [with_gconf=check])
AS_IF([test "x$with_gconf" != xyes],        
    [PKG_CHECK_MODULES(GLIB2_26,[glib-2.0 >= 2.26.0],[with_gconf=no with_gsettings=yes USE_GSETTINGS=1 AC_SUBST(USE_GSETTINGS) GLIB2_26_DEFINES="-DGLIB2_26_ENABLED" AC_DEFINE([GLIB2_26_ENABLED],[1],[Define to 1 if you have GLIB 2.26 or higher])],AC_MSG_NOTICE([Using GLIB < 2.26 specific features]))
    ])    
    
AC_ARG_WITH([gio],
    [AS_HELP_STRING([--with-gio],
        [Use GIO for file I/O])],
        [],
        [with_gio=check])
AS_IF([test "x$with_gio" != xno], 
    [PKG_CHECK_MODULES(GIO,[gio-2.0],[GIO_DEFINES="-DGIO_ENABLED" AC_DEFINE([GIO_ENABLED],[1],[Define to 1 if you have GIO support])],AC_MSG_NOTICE([Compiling without gio support]))
    AC_SUBST(GIO_DEFINES)
    AC_SUBST(GIO_CFLAGS)
    AC_SUBST(GIO_LIBS)
    ])
    
AC_ARG_WITH([alsa],
    [AS_HELP_STRING([--with-alsa],
        [Read volume from alsa devices])],
        [],
        [with_alsa=check])
AS_IF([test "x$with_alsa" != xno], 
    [PKG_CHECK_MODULES(ALSA, [alsa], [ALSA_DEFINES="-DHAVE_ASOUNDLIB" AC_DEFINE([HAVE_ASOUNDLIB],[1],[Define to 1 if you have asoundlib development packages])],AC_MSG_NOTICE([Compiling without asound support]))
    AC_SUBST(ALSA_DEFINES)
    AC_SUBST(ALSA_CFLAGS)
    AC_SUBST(ALSA_LIBS)
    ])
    
AC_ARG_WITH([pulseaudio],
    [AS_HELP_STRING([--with-pulseaudio],
        [PulseAudio device and volume support])],
        [],
        [with_pulseaudio=check])
AS_IF([test "x$with_pulseaudio" != xno], 
	[PKG_CHECK_MODULES(PULSE, [libpulse libpulse-mainloop-glib],[AC_DEFINE([HAVE_PULSEAUDIO],[1],[Define to 1 if you have PulseAudio development packages])],AC_MSG_NOTICE([Compiling without PulseAudio support]))
	AC_SUBST(PULSE_DEFINES)
	AC_SUBST(PULSE_CFLAGS)
	AC_SUBST(PULSE_LIBS)
	])

    
AC_SUBST(GLIB2_26_DEFINES)

AC_OUTPUT([
Makefile
src/gmtk.pc
src/gmlib.pc
src/Makefile
po/Makefile.in])
