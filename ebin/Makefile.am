## Makefile.am
##
## Process this file with automake to produce Makefile.in

appdir = $(beamdir)
app_DATA = map.app
EXTRA_DIST = map.app

beam_DATA = map_codec.beam

map_codec.beam:	$(top_builddir)/src/map_codec.erl
	$(ERLC) $(ERLCFLAGS) $<

%.beam:	$(top_srcdir)/src/%.erl
	$(ERLC) $(ERLCFLAGS) -I $(top_builddir)/src $<

%.app:   %.app-in
	sed -e 's/%APP_NAME%/$(PACKAGE_NAME)/' \
			-e 's/%APP_VERSION%/$(PACKAGE_VERSION)/' < $< > $@ 

CLEANFILES = $(beam_DATA) $(app_DATA)

