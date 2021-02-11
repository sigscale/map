## Makefile.am
## vim: ts=3
##
## Process this file with automake to produce Makefile.in

## NOTE:  Module HTML is not created because Currently edoc_lib:is_name/1
##        requires [a-z] as first character of filename. :(

modhtml = 
#		MAP-Protocol.html \
#		MAP-CommonDataTypes.html \
#		MAP-MS-DataTypes.html \
#		MAP-CH-DataTypes.html \
#		MAP-SM-DataTypes.html \
#		MAP-GR-DataTypes.html \
#		MAP-SS-DataTypes.html \
#		MAP-LCS-DataTypes.html \
#		MAP-ER-DataTypes.html \
#		MAP-OM-DataTypes.html \
#		MAP-ExtensionDataTypes.html \
#		MAP-BS-Code.html \
#		MAP-TS-Code.html \
#		MAP-SS-Code.html \
#		MAP-Errors.html \
#		MAP-DialogueInformation.html \
#		MAP-ApplicationContexts.html \
#		MAP-MobileServiceOperations.html \
#		MAP-CallHandlingOperations.html \
#		MAP-ShortMessageServiceOperations.html \
#		MAP-Group-Call-Operations.html \
#		MAP-LocationServiceOperations.html \
#		MAP-SupplementaryServiceOperations.html \
#		MAP-OperationAndMaintenanceOperations.html \
#		MobileDomainDefinitions.html

doc_DATA = overview.edoc $(modhtml) \
		index.html modules-frame.html overview-summary.html \
		stylesheet.css sigscale-logo.png

overview.edoc: overview.edoc-in
	sed -e 's!%VERSION%!$(VERSION)!' \
			-e 's!%DESCRIPTION%!$(PACKAGE)!' < $< > $@

index.html: overview.edoc
	$(ERL) -noshell -run edoc_run application \
			"'$(PACKAGE_NAME)'" "'$(top_builddir)'" \
			'[{sort_functions,false},{private,true},{todo,true},{source_path,["$(top_builddir)/src"]}]'
	for i in `ls *.html`; do \
			sed -e 's!erlang logo!sigscale logo!' \
					-e 's!href=\"http://www.erlang.org/\"!href=\"http://www.sigscale.org/\"!' \
					-e 's!erlang.png!sigscale-logo.png!' $$i > $$i.tmp; \
			mv $$i.tmp $$i; \
	done
	-cp -n $(top_srcdir)/doc/sigscale-logo.png .

CLEANFILES = overview.edoc edoc-info index.html \
		modules-frame.html overview-summary.html packages-frame.html \
		stylesheet.css erlang.png sigscale-logo.png

