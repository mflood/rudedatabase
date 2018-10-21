# Process this file with autoconf to produce a configure script.
#
# Copyright (C) 2002, 2003, 2004, 2005 Matthew Flood
# See file AUTHORS for contact information
#
# This file is part of RudeDatabase.
#
# RudeDatabase is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2, or (at your option)
# any later version.
# 
# RudeDatabase is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
# 
# You should have received a copy of the GNU General Public License
# along with RudeDatabase; (see COPYING) if not, write to the Free Software
# Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA
# 02111-1307, USA.
#------------------------------------------------------------------------

AC_INIT(RudeDatabase, 4.1.0, matt@rudeserver.com, rudedatabase)
AC_CANONICAL_TARGET([])
AM_INIT_AUTOMAKE(rudedatabase, 4.1.0)

dnl Copyright (C) 2002 Ben Goodwin
dnl This file is part of the nss-mysql library.
dnl
dnl The nss-mysql library is free software; you can redistribute it and/or
dnl modify it under the terms of the GNU General Public License as published
dnl by the Free Software Foundation; either version 2 of the License, or
dnl (at your option) any later version.
dnl
dnl The nss-mysql library is distributed in the hope that it will be useful,
dnl but WITHOUT ANY WARRANTY; without even the implied warranty of
dnl MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
dnl GNU General Public License for more details.
dnl
dnl You should have received a copy of the GNU General Public License
dnl along with the nss-mysql library; if not, write to the Free Software
dnl Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  USA
dnl
dnl $Id: acinclude.m4,v 1.10 2004/04/10 03:55:37 cinergi Exp $

AC_DEFUN([FIND_MYSQL],[

baselist="$with_mysql \
          /usr \
          /usr/local \
          /usr/local/mysql \
          /opt/local \
          /opt/local/mysql"

AC_MSG_CHECKING([for MySQL headers])
for f in $baselist; do
    if test -f "$f/include/mysql/mysql.h"
    then
        MYSQL_INC_DIR="$f/include/mysql"
        break
    fi

    if test -f "$f/include/mysql.h"
    then
        MYSQL_INC_DIR="$f/include"
        break
    fi
done

if test -n "$MYSQL_INC_DIR"
then
    AC_MSG_RESULT([$MYSQL_INC_DIR])
    CPPFLAGS="-I $MYSQL_INC_DIR $CPPFLAGS"
else
    AC_MSG_ERROR([Cannot locate MySQL headers.  Try using --with-mysql=DIR])
fi

AC_MSG_CHECKING([for MySQL libraries])
dnl Check for share first, then static, such that static
dnl will take precedence
for f in $baselist; do
    if test -f "$f/lib/libmysqlclient.so"
    then
        MYSQL_LIB_DIR="$f/lib"
        break
    fi

    if test -f "$f/lib/mysql/libmysqlclient.so"
    then
        MYSQL_LIB_DIR="$f/lib/mysql"
        break
    fi
done

for f in $baselist; do
    if test -f "$f/lib/libmysqlclient.a"
    then
        MYSQL_LIB_DIR="$f/lib"
        break
    fi

    if test -f "$f/lib/mysql/libmysqlclient.a"
    then
        MYSQL_LIB_DIR="$f/lib/mysql"
        break
    fi
done

if test -n "$MYSQL_LIB_DIR"
then
    AC_MSG_RESULT([$MYSQL_LIB_DIR])
    LDFLAGS="-L$MYSQL_LIB_DIR $LDFLAGS"
else
    AC_MSG_ERROR([Cannot locate MySQL libraries.  Try using --with-mysql=DIR])
fi

 ])


# Checks for programs.
AC_PROG_CXX
AC_PROG_CC
AM_PROG_LIBTOOL

# Checks for libraries.

# Checks for header files.
AC_HEADER_STDC


FIND_MYSQL()

AC_CHECK_HEADERS([mysql/mysql.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_CONST
AC_C_INLINE
AC_TYPE_SIZE_T

AC_OUTPUT(Makefile )


