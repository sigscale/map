## Makefile.am
##
## Process this file with automake to produce Makefile.in

noinst_DATA =	map_codec.erl
einclude_DATA = map_codec.hrl

map_codec.hrl: map_codec.erl

map_codec.erl:	$(top_srcdir)/asn_src/map_codec.set.asn1
	$(ERLC) $(ERLCFLAGS) +noobj $<

CLEANFILES = $(noinst_DATA) map_codec.asn1db map_codec.hrl

