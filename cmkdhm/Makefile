TARGET := /usr/share/X11/xkb/symbols/us
SOURCE := cmkdhm
TARGET_GE := /usr/share/X11/xkb/symbols/ge
SOURCE_GE := cmkdhm-ge

all: reinstall

install: $(SOURCE) $(TARGET)
	echo '//CmkDHm//BEGIN' >> $(TARGET)
	cat $(SOURCE) >> $(TARGET)
	echo '//CmkDHm//END' >> $(TARGET)

install_ge: $(SOURCE_GE) $(TARGET_GE)
	echo '//CmkDHm//BEGIN' >> $(TARGET_GE)
	cat $(SOURCE_GE) >> $(TARGET_GE)
	echo '//CmkDHm//END' >> $(TARGET_GE)

uninstall: $(TARGET)
	sed -i '/^\/\/CmkDHm\/\/BEGIN$$/,/^\/\/CmkDHm\/\/END$$/d' $<

uninstall_ge: $(TARGET_GE)
	sed -i '/^\/\/CmkDHm\/\/BEGIN$$/,/^\/\/CmkDHm\/\/END$$/d' $<


reinstall:
	$(MAKE) uninstall
	$(MAKE) uninstall_ge
	$(MAKE) install
	$(MAKE) install_ge

.PHONY: all install install_ge uninstall uninstall_ge reinstall
