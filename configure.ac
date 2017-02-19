#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([libfcgi], [v1.21], [toshic@github])
AC_CONFIG_SRCDIR([fcgi_config.h.in])
AM_CONFIG_HEADER(fcgi_config.h)
AM_INIT_AUTOMAKE([1.10 foreign -Wall -Werror])

LT_INIT
AC_CONFIG_MACRO_DIR([m4])

# Checks for programs.
AC_PROG_CXX
AC_PROG_AWK
AC_PROG_CC
AC_PROG_CPP
AC_PROG_INSTALL
AC_PROG_LN_S
AC_PROG_MAKE_SET
AM_PROG_CC_C_O
AC_PROG_LIBTOOL

# Checks for header files.
AC_CHECK_HEADERS([arpa/inet.h fcntl.h limits.h memory.h netdb.h netinet/in.h stdlib.h string.h sys/param.h sys/socket.h sys/time.h sys/timeb.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_TYPE_PID_T
AC_TYPE_SIZE_T

# Checks for library functions.
AC_FUNC_FORK
AC_FUNC_MALLOC
AC_FUNC_REALLOC
AC_CHECK_FUNCS([atexit dup2 ftime gethostbyname inet_ntoa memchr memset putenv select socket strchr strerror strrchr strspn strstr strtol])

AC_SUBST(LIBFCGIXX)
AC_SUBST(ECHO_CPP)

AC_LANG([C])

AC_CHECK_LIB([nsl],       [gethostbyname])
AC_CHECK_LIB([socket],    [socket]) 

m4_include([m4/acx_pthread.m4])
ACX_PTHREAD([THREADED=threaded${EXEEXT}])
AC_SUBST([THREADED])

FCGI_COMMON_CHECKS

SYSTEM=unix
AC_SUBST([SYSTEM])

AC_REPLACE_FUNCS([strerror])

AC_C_INLINE

AC_CONFIG_FILES([Makefile
                 cgi-fcgi/Makefile
                 examples/Makefile
                 include/Makefile
                 libfcgi/Makefile])

AC_OUTPUT