#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([Deepin Terminal], [2.16], [wangyong@deepin.com], [deepin-terminal], [https://github.com/manateelazycat/deepin-terminal])
AC_CONFIG_SRCDIR([project_path.c])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_AUX_DIR([build-aux])

AM_INIT_AUTOMAKE([foreign subdir-objects])
AM_PROG_VALAC(
  [0.32],
  [AC_MSG_NOTICE([valid Vala compiler found])],
  [AC_MSG_ERROR([Vala compiler not found])])

# Checks for programs.
AC_PROG_CC
AC_PROG_INSTALL
AC_PROG_LN_S

# Checks for libraries.
AC_CHECK_LIB([m], [sin])

# Checks for header files.
AC_CHECK_HEADERS([stdlib.h string.h])

# Checks for typedefs, structures, and compiler characteristics.

# Checks for library functions.
AC_FUNC_MALLOC
AC_FUNC_REALLOC

# Calling pkg-config to retrieve buildflags
PKG_CHECK_MODULES([GTK_3], [gtk+-3.0 >= 3.20])
PKG_CHECK_MODULES([VTE2_91], [vte-2.91])
PKG_CHECK_MODULES([GEE_0_8], [gee-0.8])
PKG_CHECK_MODULES([JSON_GLIB_1_0], [json-glib-1.0])
PKG_CHECK_MODULES([GIO_2_0], [gio-2.0])
PKG_CHECK_MODULES([LIBWNCK_3_0], [libwnck-3.0])
PKG_CHECK_MODULES([GDK_X11_3_0],[gdk-x11-3.0 >= 3.20])
PKG_CHECK_MODULES([XCB], [xcb])
PKG_CHECK_MODULES([X11_XCB], [x11-xcb])
PKG_CHECK_MODULES([LIBSECRET_1], [libsecret-1])
PKG_CHECK_MODULES([FONTCONFIG], [fontconfig])

CFLAGS="$CFLAGS $GTK_3_CFLAGS $VTE2_91_CFLAGS $GEE_0_8_CFLAGS $JSON_GLIB_1_0_CFLAGS \
$GIO_2_0_CFLAGS $LIBWNCK_3_0_CFLAGS $GDK_X11_3_0_CFLAGS $XCB_CFLAGS \
$X11_XCB_CFLAGS $LIBSECRET_1_CFLAGS $FONTCONFIG_CFLAGS"

LIBS="$LIBS $GTK_3_LIBS $VTE2_91_LIBS $GEE_0_8_LIBS $JSON_GLIB_1_0_LIBS \
$GIO_2_0_GLIBS $LIBWNCK_3_0_LIBS $GDK_X11_3_0_LIBS $XCB_LIBS $X11_XCB_LIBS \
$LIBSECRET_1_LIBS $FONTCONFIG_LIBS"

AC_CONFIG_FILES([Makefile])
AC_OUTPUT
