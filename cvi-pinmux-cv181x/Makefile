prefix  = /usr/
VERSION = 1.0.0
PACKAGENAME = cvi-pinmux-cv181x
all: cvi_pinmux

cvi_pinmux: devmem.c cvi_pinmux.c
	$(CC) $(CPPFLAGS) $(CFLAGS) $(LDCFLAGS) -o $@ $^

install: cvi_pinmux
	install -D cvi_pinmux $(DESTDIR)$(prefix)/bin/cvi_pinmux

clean:
	-rm -f cvi_pinmux

distclean: clean

uninstall:
	-rm -f $(DESTDIR)$(prefix)/bin/cvi_pinmux

package-prepare:
	@tar -czf ../$(PACKAGENAME)-$(VERSION).tar.gz .
	@-dh_make -f ../$(PACKAGENAME)-$(VERSION).tar.gz -p $(PACKAGENAME)_$(VERSION) --copyright gpl2 -s -y 

.PHONY: all install clean distclean uninstall package-prepare