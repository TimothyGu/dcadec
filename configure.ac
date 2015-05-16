AC_INIT([dcadec], [0.0.0], [http://example.com])
AC_CONFIG_AUX_DIR(.)
AC_CONFIG_MACRO_DIR([m4])
AM_INIT_AUTOMAKE([tar-ustar foreign])
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

dnl Various options for configure
AC_ARG_ENABLE([dcadec],
            [AS_HELP_STRING([--disable-dcadec],
                [disable building dcadec program])],
            [dec=$enableval], [dec=yes])
AC_ARG_ENABLE([dcacut],
            [AS_HELP_STRING([--enable-dcacut],
                [enable building dcacut program])],
            [cut=$enableval], [cut=no])
AC_ARG_ENABLE([small],
            [AS_HELP_STRING([--enable-small],
                [build a smaller library with less APIs])],
            [small=$enableval], [small=no])
if test "x$dec" = xyes -o "x$cut" = xyes && test "x$small" = xyes
then
    AC_MSG_ERROR([dcadec and dcacut conflict with --enable-small])
fi

dnl Automake conditionals to set
AM_CONDITIONAL(DCADEC, test x$dec   = xyes)
AM_CONDITIONAL(DCACUT, test x$cut   = xyes)
AM_CONDITIONAL(SMALL,  test x$small = xyes)

: ${CFLAGS='-g -O3 -ffast-math'}
AC_PROG_CC
AC_PROG_CC_C99
AC_FUNC_FSEEKO
AC_SYS_LARGEFILE
LT_INIT

AC_SEARCH_LIBS([sin], [m])

dnl soname version to use
dnl goes by ‘current[:revision[:age]]’ with the soname ending up as
dnl current.age.revision
DCADEC_VERSION=0:0:0

LIBS_PRIVATE="$LIBS"
AC_SUBST(DCADEC_VERSION)
AC_SUBST(LIBS_PRIVATE)

AC_CONFIG_FILES([Makefile
                 dcadec.pc])
AC_OUTPUT
