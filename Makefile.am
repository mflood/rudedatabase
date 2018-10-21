# Makefile.am
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

lib_LTLIBRARIES = librudedatabase.la

librudedatabase_la_SOURCES = 	src/database.cpp \
	src/database.h \
	src/implementation.cpp \
	src/implementation.h

librudedatabase_la_LDFLAGS = -version-info 4:1:0

#  -------------------------------------
librudedatabase_la_LIBADD = -lmysqlclient
#----------------------------------------

pkginclude_HEADERS = src/database.h
pkgincludedir = $(includedir)/rude

man_MANS = man3/rudedatabase.3

EXTRA_DIST = $(man_MANS)

AM_CPPFLAGS = -I/usr/include/mysql

AUTOMAKE_OPTIONS = gnits dist-bzip2 dist-shar dist-zip

