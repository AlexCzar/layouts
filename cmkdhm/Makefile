TARGET := /usr/share/X11/xkb/symbols/us
SOURCE := cmkdhm

all: reinstall

install: $(SOURCE) $(TARGET)
	echo '//CmkDHm//BEGIN' >> $(TARGET)
	cat $(SOURCE) >> $(TARGET)
	echo '//CmkDHm//END' >> $(TARGET)

uninstall: $(TARGET)
	sed -i '/^\/\/CmkDHm\/\/BEGIN$$/,/^\/\/CmkDHm\/\/END$$/d' $<

reinstall:
	$(MAKE) uninstall
	$(MAKE) install

.PHONY: all install uninstall reinstall
