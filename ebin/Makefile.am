## Makefile.am
##
## Process this file with automake to produce Makefile.in

appdir = $(beamdir)
app_DATA = map.app map.appup
EXTRA_DIST = map.app map.appup

beam_DATA = MAP-Protocol.beam \
		MAP-CommonDataTypes.beam \
		MAP-MS-DataTypes.beam \
		MAP-CH-DataTypes.beam \
		MAP-SM-DataTypes.beam \
		MAP-GR-DataTypes.beam \
		MAP-SS-DataTypes.beam \
		MAP-LCS-DataTypes.beam \
		MAP-ER-DataTypes.beam \
		MAP-OM-DataTypes.beam \
		MAP-ExtensionDataTypes.beam \
		MAP-BS-Code.beam \
		MAP-TS-Code.beam \
		MAP-SS-Code.beam \
		MAP-Errors.beam \
		MAP-DialogueInformation.beam \
		MAP-ApplicationContexts.beam \
		MAP-MobileServiceOperations.beam \
		MAP-CallHandlingOperations.beam \
		MAP-ShortMessageServiceOperations.beam \
		MAP-Group-Call-Operations.beam \
		MAP-LocationServiceOperations.beam \
		MAP-SupplementaryServiceOperations.beam \
		MAP-OperationAndMaintenanceOperations.beam \
		MobileDomainDefinitions.beam

%.beam:	$(top_builddir)/src/%.erl
	$(ERLC) $(ERLCFLAGS) -I $(top_builddir)/src $<

%.app:   %.app-in
	sed -e 's/%APP_NAME%/$(PACKAGE_NAME)/' \
			-e 's/%APP_VERSION%/$(PACKAGE_VERSION)/' < $< > $@ 

CLEANFILES = $(beam_DATA) $(app_DATA)

