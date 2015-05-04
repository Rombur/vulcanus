# Copyright (c) 2015, Bruno Turcksin.
#
# This file is subject to the Modified BSD License and may not be distributed
# without copyright and license information. Please refer to the file
# license.txt for the text and further information on this license.

CMAKE_MINIMUM_REQUIRED(VERSION 3.1)

# Need to Fortran.
ENABLE_LANGUAGE(Fortran)

PROJECT(vulcanus)

# FreeBSD requires a special flag to compile Fortran code.
IF(${CMAKE_SYSTEM_NAME} MATCHES "FreeBSD")
  SET(CMAKE_Fortran_FLAGS "-rpath=/usr/local/lib/gcc48")
ENDIF(${CMAKE_SYSTEM_NAME} MATCHES "FreeBSD")

ADD_EXECUTABLE(vulcanus src/vulcanus.f90)
