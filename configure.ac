dnl Process this file with autoconf to produce a configure script.
dnl Created by Anjuta application wizard.

AC_INIT(gmtk, 1.0.6)
m4_ifdef([AM_SILENT_RULES],[AM_SILENT_RULES([yes])])

AM_INIT_AUTOMAKE(AC_PACKAGE_NAME, AC_PACKAGE_VERSION)
AC_CONFIG_HEADERS([config.h])
AM_MAINTAINER_MODE([enable])

AC_PROG_CC
AC_CONFIG_MACRO_DIR([m4])



dnl ***************************************************************************
dnl Internatinalization
dnl ***************************************************************************
GETTEXT_PACKAGE=gmtk
AC_SUBST(GETTEXT_PACKAGE)
AC_DEFINE_UNQUOTED(GETTEXT_PACKAGE,"$GETTEXT_PACKAGE", [GETTEXT package name])


dnl Add the languages which your application supports here.
ALL_LINGUAS="ar bg ca cs da de el en_GB es et eu fi fo fr fy gl he hr hu id it ja ko lt nl pl pt pt_BR ro ru si sr sr@latin sv th tr ug uk vi zh_CN zh_HK zh_TW"
AC_SUBST(ALL_LINGUAS)
AM_GLIB_GNU_GETTEXT

IT_PROG_INTLTOOL([0.35.0])


####################################################################
# Windows check
####################################################################

AC_MSG_CHECKING(for WIN32)
AC_TRY_COMPILE(,
	[
	#ifndef WIN32
	#error
	#endif
	],
	native_win32=yes; AC_MSG_RESULT(yes),
	native_win32=no; AC_MSG_RESULT(no),
)

AM_CONDITIONAL(OS_WIN32, test "$native_win32" = "yes")

if test "$native_win32" = "yes" ; then
   AC_DEFINE(OS_WIN32, 1, [Define if we are on win32])
fi

AM_PROG_LIBTOOL

PKG_CHECK_MODULES([X11], [x11],[AC_DEFINE([X11_ENABLED],[1],[Define to 1 if X11 support is needed])],[AC_MSG_NOTICE([Compiling without X11 support])])
AC_SUBST(X11_LIBS)

AC_CHECK_LIB([m],[floor])

AC_ARG_ENABLE(gtk3,
    AC_HELP_STRING([--enable-gtk3],[compile using GTK3]),
    [case "${enableval}" in
    yes) ENABLE_GTK3=yes
         PKG_CHECK_MODULES(GTK,[gtk+-3.0 >= 3 glib-2.0 gthread-2.0],[ENABLE_GTK3=yes],[ENABLE_GTK3=no]);;
    no) ENABLE_GTK3=no;;
    *) AC_MSG_ERROR(bad value ${enableval} for --enable-gtk3) ;;
    esac], 
    [ENABLE_GTK3=check])

AS_IF([test "x$ENABLE_GTK3" = xcheck],        
        [ENABLE_GTK3=no
        PKG_CHECK_MODULES(GTK,[gtk+-3.0 >= 3 glib-2.0 gthread-2.0],[ENABLE_GTK3=yes],[ENABLE_GTK3=no])
        ])    
    
AS_IF([test "x$ENABLE_GTK3" = "xyes"],   
    [
   
    ENABLE_GTK2=no 
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
    
    PKG_CHECK_MODULES(GLIB2_18,[glib-2.0 >= 2.18.0],[GLIB2_18_DEFINES="-DGLIB2_18_ENABLED" AC_DEFINE([GLIB2_18_ENABLED],[1],[Define to 1 if you have GLIB 2.18 or higher])],AC_MSG_NOTICE([Using GLIB 2.18 features]))
    AC_SUBST(GLIB2_18_DEFINES)

    PKG_CHECK_MODULES(GLIB2_24,[glib-2.0 >= 2.24.0],[GLIB2_24_DEFINES="-DGLIB2_24_ENABLED" AC_DEFINE([GLIB2_24_ENABLED],[1],[Define to 1 if you have GLIB 2.24 or higher])],AC_MSG_NOTICE([Using GLIB 2.24 features]))
    AC_SUBST(GLIB2_24_DEFINES)

    PKG_CHECK_MODULES(GLIB2_26,[glib-2.0 >= 2.26.0],[GLIB2_26_DEFINES="-DGLIB2_26_ENABLED" AC_DEFINE([GLIB2_26_ENABLED],[1],[Define to 1 if you have GLIB 2.26 or higher])],AC_MSG_NOTICE([Using GLIB 2.26 features]))
    AC_SUBST(GLIB2_26_DEFINES)
    
    ])

AS_IF([test "x$ENABLE_GTK3" != "xyes"],   
    [

    ENABLE_GTK2=yes
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

    PKG_CHECK_MODULES(GLIB2_14,[glib-2.0 >= 2.14.0],[GLIB2_14_DEFINES="-DGLIB2_14_ENABLED" AC_DEFINE([GLIB2_14_ENABLED],[1],[Define to 1 if you have GLIB 2.14 or higher])],AC_MSG_NOTICE([Using GLIB 2.14 features]))
    AC_SUBST(GLIB2_14_DEFINES)

    PKG_CHECK_MODULES(GLIB2_18,[glib-2.0 >= 2.18.0],[GLIB2_18_DEFINES="-DGLIB2_18_ENABLED" AC_DEFINE([GLIB2_18_ENABLED],[1],[Define to 1 if you have GLIB 2.18 or higher])],AC_MSG_NOTICE([Using GLIB 2.18 features]))
    AC_SUBST(GLIB2_18_DEFINES)

    PKG_CHECK_MODULES(GLIB2_24,[glib-2.0 >= 2.24.0],[GLIB2_24_DEFINES="-DGLIB2_24_ENABLED" AC_DEFINE([GLIB2_24_ENABLED],[1],[Define to 1 if you have GLIB 2.24 or higher])],AC_MSG_NOTICE([Using GLIB 2.24 features]))
    AC_SUBST(GLIB2_24_DEFINES)

    PKG_CHECK_MODULES(GLIB2_26,[glib-2.0 >= 2.26.0],[GLIB2_26_DEFINES="-DGLIB2_26_ENABLED" AC_DEFINE([GLIB2_26_ENABLED],[1],[Define to 1 if you have GLIB 2.26 or higher])],AC_MSG_NOTICE([Using GLIB 2.26 features]))
    AC_SUBST(GLIB2_26_DEFINES)

])

AC_SUBST(ENABLE_GTK2)
AC_SUBST(ENABLE_GTK3)

AC_ARG_ENABLE([gsettings],
    AC_HELP_STRING([--enable-gsettings],[compile using GSettings for preference storage]),
    [case "${enableval}" in
    yes) enable_gsettings=yes ;;
    no) enable_gesttings=no ;;
    *) AC_MSG_ERROR(bad value ${enableval} for --enable-gsettings) ;;
    esac], 
    [enable_gsettings=check])

AC_ARG_ENABLE([gconf],
    AC_HELP_STRING([--enable-gconf],[compile using GConf for preference storage]),
    [case "${enableval}" in
    yes) enable_gconf=yes ;;
    no) enable_gconf=no ;;
    *) AC_MSG_ERROR(bad value ${enableval} for --enable-gconf) ;;
    esac], 
    [enable_gconf=check])

AC_ARG_ENABLE([keystore],
    AC_HELP_STRING([--enable-keystore],[compile using KeyStore for preference storage]),
    [case "${enableval}" in
    yes) enable_keystore=yes ;;
    no) enable_keystore=no ;;
    *) AC_MSG_ERROR(bad value ${enableval} for --enable-keystore) ;;
    esac], 
    [enable_keystore=check])

if test "$enable_keystore" = "yes" || test "$enable_gconf" = "yes" || test "$enable_gsettings" = "yes"; then
    AC_MSG_NOTICE([Using specified backend])    
else
    AC_MSG_NOTICE([Determining backend])

    PKG_CHECK_MODULES(GCONF, [gconf-2.0], [enable_gconf=yes], [enable_gconf=no])
    PKG_CHECK_MODULES(GLIB2_26,[glib-2.0 >= 2.26.0],[enable_gsettings=yes], [enable_gsettings=no])

    if test "$enable_gconf" = "no" && test "$enable_gsettings" = "no"; then
        enable_keystore=yes
    fi
fi

if test "$enable_keystore" = "yes"; then
    AC_MSG_NOTICE([Using keystore backend])
    use_gsettings=no
    USE_GSETTINGS=0
    use_gconf=no
    USE_GCONF=0
    AM_CONDITIONAL([GCONF_SCHEMAS_INSTALL],[false])
    GSETTINGS_RULES=""
    AC_SUBST(GSETTINGS_RULES)
    BACKEND=keystore
    AC_SUBST(BACKEND)   
elif test "$enable_gsettings" = "yes"; then
    AC_MSG_NOTICE([Using GSettings backend])
    use_gsettings=yes
    USE_GSETTINGS=1
    use_gconf=no
    USE_GCONF=0
    AC_DEFINE([HAVE_GSETTINGS],[1],[Define to 1 to use GSettings to store preferences])
    AM_CONDITIONAL([GCONF_SCHEMAS_INSTALL],[false])
    GLIB_GSETTINGS
    BACKEND=gsettings
    AC_SUBST(BACKEND)   
elif test "$enable_gconf" = "yes"; then
    AC_MSG_NOTICE([Using GConf backend])
    use_gsettings=no
    USE_GSETTINGS=0
    use_gconf=yes
    USE_GCONF=1
    PKG_CHECK_MODULES(GCONF, [gconf-2.0], [enable_gconf=yes], [enable_gconf=no])
    AC_DEFINE([HAVE_GCONF],[1],[Define to 1 to use GConf to store preferences])
    AM_GCONF_SOURCE_2
    GSETTINGS_RULES=""
    AC_SUBST(GSETTINGS_RULES)    
    BACKEND=gconf
    AC_SUBST(BACKEND)   
fi

AC_SUBST(USE_GCONF)
AC_SUBST(USE_GSETTINGS)

   
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
gmtk.spec
src/gmtk.pc
src/gmlib.pc
src/Makefile
po/Makefile.in])
