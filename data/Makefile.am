dbusservicedir = $(DBUS_SERVICE_DIR)
dbusservice_DATA = \
	com.canonical.settings.network.service

EXTRA_DIST = \
	    com.canonical.settings.network.service.in

CLEANFILES = $(dbusservice_DATA)

com.canonical.settings.network.service: com.canonical.settings.network.service.in Makefile
	sed -e 's|@NETWORK_SERVICE[@]|$(pkglibdir)/indicator-network-menu-server|g' $< >$@

