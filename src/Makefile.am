## Makefile.am
##
## Process this file with automake to produce Makefile.in

erl_DATA = MAP-Protocol.erl \
		MAP-CommonDataTypes.erl \
		MAP-MS-DataTypes.erl \
		MAP-CH-DataTypes.erl \
		MAP-SM-DataTypes.erl \
		MAP-GR-DataTypes.erl \
		MAP-SS-DataTypes.erl \
		MAP-LCS-DataTypes.erl \
		MAP-ER-DataTypes.erl \
		MAP-OM-DataTypes.erl \
		MAP-ExtensionDataTypes.erl \
		MAP-BS-Code.erl \
		MAP-TS-Code.erl \
		MAP-SS-Code.erl \
		MAP-Errors.erl \
		MAP-DialogueInformation.erl \
		MAP-ApplicationContexts.erl \
		MAP-MobileServiceOperations.erl \
		MAP-CallHandlingOperations.erl \
		MAP-ShortMessageServiceOperations.erl \
		MAP-Group-Call-Operations.erl \
		MAP-LocationServiceOperations.erl \
		MAP-SupplementaryServiceOperations.erl \
		MAP-OperationAndMaintenanceOperations.erl \
		MobileDomainDefinitions.erl

einclude_DATA = MAP-CommonDataTypes.hrl \
		MAP-MS-DataTypes.hrl \
		MAP-CH-DataTypes.hrl \
		MAP-SM-DataTypes.hrl \
		MAP-GR-DataTypes.hrl \
		MAP-SS-DataTypes.hrl \
		MAP-LCS-DataTypes.hrl \
		MAP-ER-DataTypes.hrl \
		MAP-OM-DataTypes.hrl \
		MAP-ExtensionDataTypes.hrl \
		MAP-BS-Code.hrl \
		MAP-TS-Code.hrl \
		MAP-SS-Code.hrl \
		MAP-DialogueInformation.hrl \
		MAP-ApplicationContexts.hrl \
		MobileDomainDefinitions.hrl

%.erl %.hrl: $(top_srcdir)/asn_src/%.asn1
	$(ERLC) $(ERLCFLAGS) +ber +noobj $<

CLEANFILES = $(erl_DATA) \
		$(einclude_DATA) \
		*.asn1db
