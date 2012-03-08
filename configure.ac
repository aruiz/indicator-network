
AC_INIT(chewie, 0.1, alberto.ruiz@canonical.com)
AC_COPYRIGHT([Copyright 2011,2012 Canonical])

AC_PREREQ(2.62)

AM_CONFIG_HEADER(config.h)
AM_INIT_AUTOMAKE(chewie, 0.1)

AM_MAINTAINER_MODE

AC_ISC_POSIX
AC_PROG_CC
AM_PROG_CC_C_O
AC_STDC_HEADERS
AC_PROG_LIBTOOL

AC_SUBST(VERSION)
AC_CONFIG_MACRO_DIR([m4])

m4_ifdef([AM_SILENT_RULES],[AM_SILENT_RULES([yes])])

AC_PATH_PROG([GLIB_MKENUMS], [glib-mkenums])

###########################
# Dependencies - GLib
###########################

GLIB_REQUIRED_VERSION=2.26
PKG_CHECK_MODULES(GLIB, glib-2.0 >= $GLIB_REQUIRED_VERSION
                        gio-2.0 >= $GLIB_REQUIRED_VERSION)
AC_SUBST(GLIB_LIBS)
AC_SUBST(GLIB_CFLAGS)

###########################
# Dependencies - Dbusmenu 
###########################

DBUSMENU_REQUIRED_VERSION=0.4
PKG_CHECK_MODULES(DBUSMENU, dbusmenu-glib-0.4 >= $DBUSMENU_REQUIRED_VERSION)
AC_SUBST(DBUSMENU_LIBS)
AC_SUBST(DBUSMENU_CFLAGS)

#################################
# Dependencies - NetworkManager
#################################

NM_REQUIRED_VERSION=0.9
PKG_CHECK_MODULES(NM, libnm-glib >= $NM_REQUIRED_VERSION
                      libnm-util >= $NM_REQUIRED_VERSION)
AC_SUBST(NM_LIBS)
AC_SUBST(NM_CFLAGS)

################################
# Dependencies - Gtk+
################################

GTK_REQUIRED_VERSION=3.0
PKG_CHECK_MODULES(GTK, gtk+-3.0 >= $GTK_REQUIRED_VERSION)
AC_SUBST(GTK_LIBS)
AC_SUBST(NM_CFLAGS)

###########################
# Vala Compiler
###########################

AC_PATH_PROG([VALAC], [valac])
AM_CONDITIONAL([HAVE_VALAC], [test -n "$VALAC"])

############################
# GSettings schema compiler
############################

AC_PATH_PROG([GSCHEMA_COMPILER], [glib-compile-schemas])
AM_CONDITIONAL([HAVE_GSCHEMA_COMPILER], [test -n "$GSCHEMA_COMPILER"])

###########################
# Files
###########################

AC_OUTPUT([
Makefile
network/Makefile
exportmenu/Makefile
agent/Makefile
tests/Makefile
])