prefix  = /usr/
VERSION = 1.0.0
PACKAGENAME = duo-pinmux
all: duo-pinmux

duo-pinmux: src/devmem.c src/duo_pinmux.c
	$(CC) -Iinclude $(CPPFLAGS) $(CFLAGS) $(LDCFLAGS) -o $@ $^

install: duo-pinmux
	install -D duo-pinmux $(DESTDIR)$(prefix)/bin/duo-pinmux

clean:
	-rm -f duo-pinmux

distclean: clean

uninstall:
	-rm -f $(DESTDIR)$(prefix)/bin/duo-pinmux

package-prepare:
	@tar -czf ../$(PACKAGENAME)-$(VERSION).tar.gz .
	@-dh_make -f ../$(PACKAGENAME)-$(VERSION).tar.gz -p $(PACKAGENAME)_$(VERSION) --copyright gpl2 -s -y 

.PHONY: all install clean distclean uninstall package-prepare