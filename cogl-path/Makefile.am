include $(top_srcdir)/build/autotools/Makefile.am.silent

NULL =

BUILT_SOURCES =

CLEANFILES =
DISTCLEANFILES =

EXTRA_DIST =

# tesselator sources
cogl_tesselator_sources = \
	$(srcdir)/tesselator/dict-list.h 	\
	$(srcdir)/tesselator/dict.c 		\
	$(srcdir)/tesselator/dict.h 		\
	$(srcdir)/tesselator/geom.c 		\
	$(srcdir)/tesselator/geom.h 		\
	$(srcdir)/tesselator/gluos.h 		\
	$(srcdir)/tesselator/memalloc.h 	\
	$(srcdir)/tesselator/mesh.c 		\
	$(srcdir)/tesselator/mesh.h 		\
	$(srcdir)/tesselator/normal.c 		\
	$(srcdir)/tesselator/normal.h 		\
	$(srcdir)/tesselator/priorityq-heap.h 	\
	$(srcdir)/tesselator/priorityq-sort.h 	\
	$(srcdir)/tesselator/priorityq.c 	\
	$(srcdir)/tesselator/priorityq.h 	\
	$(srcdir)/tesselator/render.c 		\
	$(srcdir)/tesselator/render.h 		\
	$(srcdir)/tesselator/sweep.c 		\
	$(srcdir)/tesselator/sweep.h 		\
	$(srcdir)/tesselator/tess.c 		\
	$(srcdir)/tesselator/tess.h 		\
	$(srcdir)/tesselator/tesselator.h 	\
	$(srcdir)/tesselator/tessmono.c 	\
	$(srcdir)/tesselator/tessmono.h 	\
	$(srcdir)/tesselator/GL/glu.h 		\
	$(NULL)

source_c = \
	$(cogl_tesselator_sources) \
	cogl-path-private.h \
	cogl1-path.c \
	cogl-path.c \
	$(NULL)

EXTRA_DIST += \
	$(srcdir)/tesselator/README 		\
	$(srcdir)/tesselator/priorityq-heap.c	\
	$(NULL)

source_1_x_h = \
	$(srcdir)/cogl-path-types.h \
	$(srcdir)/cogl1-path-functions.h \
	$(NULL)

source_h = \
	cogl-path.h \
	$(source_1_x_h) \
	cogl2-path-functions.h \
	$(NULL)

if USE_GLIB
# glib-mkenums rules
glib_enum_h = cogl-path-enum-types.h
glib_enum_c = cogl-path-enum-types.c
glib_enum_headers = $(source_1_x_h)
include $(top_srcdir)/build/autotools/Makefile.am.enums
endif

noinst_LTLIBRARIES = libcogl-path.la

libcogl_path_la_SOURCES = $(source_c) $(source_h)
nodist_libcogl_path_la_SOURCES = $(BUILT_SOURCES)
libcogl_path_la_CFLAGS = $(COGL_DEP_CFLAGS) $(COGL_GST_DEP_CFLAGS) $(COGL_EXTRA_CFLAGS) $(MAINTAINER_CFLAGS)

AM_CPPFLAGS = \
	-DCOGL_COMPILATION		\
	-DG_LOG_DOMAIN=\"CoglPath\"	\
	-I$(srcdir)/tesselator		\
	-I$(top_srcdir)/cogl		\
	-I$(top_builddir)/cogl		\
	-I$(top_srcdir)/cogl/winsys	\
	-I$(top_srcdir)			\
	-I$(top_builddir)

cogl_pathheadersdir = $(includedir)/cogl/cogl-path
cogl_pathheaders_HEADERS = $(source_h)
if USE_GLIB
nodist_cogl_pathheaders_HEADERS = cogl-path-enum-types.h
endif