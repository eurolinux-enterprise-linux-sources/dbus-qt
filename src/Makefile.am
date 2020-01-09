INCLUDES=-I$(top_srcdir) $(DBUS_CFLAGS) $(DBUS_QT3_CXXFLAGS)

dbusincludedir=$(includedir)/dbus-1.0/dbus

lib_LTLIBRARIES=libdbus-qt-1.la

dbusinclude_HEADERS=				\
	dbus-qt.h message.h connection.h        \
	server.h

libdbus_qt_1_la_SOURCES = 			\
	$(top_srcdir)/dbus-qthread.cpp \
	$(top_srcdir)/message.cpp \
	$(top_srcdir)/connection.cpp \
	$(top_srcdir)/integrator.cpp \
	$(top_srcdir)/server.cpp \
	$(top_srcdir)/connection.h \
	$(top_srcdir)/integrator.h \
	$(top_srcdir)/server.h


$(top_srcdir)/connection.cpp: connection.moc
$(top_srcdir)/integrator.cpp: integrator.moc
$(top_srcdir)/server.cpp: server.moc
$(top_srcdir)/connection.h: connection.moc
$(top_srcdir)/integrator.h: integrator.moc
$(top_srcdir)/server.h: server.moc

CLEANFILES=connection.moc integrator.moc server.moc

libdbus_qt_1_la_LIBADD= $(DBUS_QT3_LIBS) $(DBUS_LIBS)
libdbus_qt_1_la_LDFLAGS= -version-info 1:0 -no-undefined

%.moc: %.h
	$(QT3_MOC) $< > $@
