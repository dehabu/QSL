#
# Root QSL
#
PROJECT(QSL)
cmake_minimum_required(VERSION 2.8)

SET(qsl_sources_cpp
	qvbitcount.cpp        
	qvcomplex.cpp
	qvmath.cpp
	qvmatrix.cpp
	qvquaternion.cpp
	qvsparseblockmatrix.cpp
	qvblasdatabuffer.cpp
	qvdefines.cpp
	qvmatrixalgebra.cpp
	qvpermutation.cpp
	qvrationalnumber.cpp
	qvvector.cpp
   )

SET(qsl_sources_hpp
	qv3dpointf.h
	qvdefines.h
	qvpermutation.h
	qvvector.h
	qvbitcount.h
	qvmath.h
	qvquaternion.h
	qvblasdatabuffer.h
	qvmatrixalgebra.h
	qvrationalnumber.h
	qvcomplex.h
	qvmatrix.h
	qvsparseblockmatrix.h
   )

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR})
INCLUDE_DIRECTORIES(${QT_INCLUDES})
INCLUDE_DIRECTORIES(${GSL_INCLUDE_DIR})

SET(qsl_sources ${qsl_sources_cpp})

IF (WIN32 OR APPLE)
  ADD_LIBRARY(qsl STATIC ${qsl_sources})
ELSE (WIN32 OR APPLE)
  ADD_LIBRARY(qsl STATIC ${qsl_sources})
ENDIF (WIN32 OR APPLE)


INSTALL (TARGETS qsl DESTINATION ${LIBRARY_OUTPUT_DIRECTORY})
#INSTALL (FILES ${qsl_sources_hpp} DESTINATION include)

