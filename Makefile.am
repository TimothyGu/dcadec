ACLOCAL_AMFLAGS = -I m4
AUTOMAKE_OPTIONS = subdir-objects
AM_CFLAGS = -Wall -Wextra

pkgconfigdir = @libdir@/pkgconfig
pkgconfig_DATA = dcadec.pc

lib_LTLIBRARIES = libdcadec.la
libdcadec_la_LDFLAGS = -version-info @DCADEC_VERSION@ -no-undefined

includedir = @includedir@/libdcadec
include_HEADERS = \
@top_srcdir@/libdcadec/dca_context.h

libdcadec_la_SOURCES = \
@top_srcdir@/libdcadec/bitstream.c \
@top_srcdir@/libdcadec/common.h \
@top_srcdir@/libdcadec/compiler.h \
@top_srcdir@/libdcadec/core_decoder.c \
@top_srcdir@/libdcadec/core_decoder.h \
@top_srcdir@/libdcadec/core_huffman.h \
@top_srcdir@/libdcadec/core_tables.h \
@top_srcdir@/libdcadec/core_vectors.h \
@top_srcdir@/libdcadec/dca_context.c \
@top_srcdir@/libdcadec/dca_waveout.h \
@top_srcdir@/libdcadec/dmix_tables.c \
@top_srcdir@/libdcadec/dmix_tables.h \
@top_srcdir@/libdcadec/exss_parser.c \
@top_srcdir@/libdcadec/exss_parser.h \
@top_srcdir@/libdcadec/fir_fixed.h \
@top_srcdir@/libdcadec/fir_float.h \
@top_srcdir@/libdcadec/fixed_math.h \
@top_srcdir@/libdcadec/huffman.h \
@top_srcdir@/libdcadec/idct.h \
@top_srcdir@/libdcadec/idct_fixed.c \
@top_srcdir@/libdcadec/idct_float.c \
@top_srcdir@/libdcadec/interpolator.c \
@top_srcdir@/libdcadec/interpolator.h \
@top_srcdir@/libdcadec/interpolator_fixed.c \
@top_srcdir@/libdcadec/interpolator_float.c \
@top_srcdir@/libdcadec/ta.c \
@top_srcdir@/libdcadec/ta.h \
@top_srcdir@/libdcadec/xll_decoder.c \
@top_srcdir@/libdcadec/xll_decoder.h \
@top_srcdir@/libdcadec/xll_tables.h

if !SMALL
libdcadec_la_SOURCES += \
@top_srcdir@/libdcadec/dca_frame.c   \
@top_srcdir@/libdcadec/dca_stream.c  \
@top_srcdir@/libdcadec/dca_waveout.c

include_HEADERS += \
@top_srcdir@/libdcadec/dca_frame.h   \
@top_srcdir@/libdcadec/dca_stream.h  \
@top_srcdir@/libdcadec/dca_waveout.h
endif

# Programs
if DCADEC
bin_PROGRAMS += dcadec$(EXEEXT)

dcadec_LDADD = libdcadec.la
dcadec_SOURCES = dcadec.c
endif

if DCACUT
bin_PROGRAMS += dcacut$(EXEEXT)

dcacut_LDADD = libdcadec.la
dcacut_SOURCES = dcacut.c
endif
