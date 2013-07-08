# This file is part of MAILBOOT.
#
# MAILBOOT is free software: you can redistribute it and/or modify
# it under the terms of the GNU Lesser General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# MAILBOOT is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU Lesser General Public License for more details.
#
# You should have received a copy of the GNU Lesser General Public License
# along with MAILBOOT.  If not, see <http://www.gnu.org/licenses/>.

EXTRA_DIST = mailboot.in mailboot.service.in

CLEANFILES = mailboot mailboot.service

bin_SCRIPTS = mailboot
dist_doc_DATA = README COPYRIGHT LICENSE AUTHORS
systemdunit_DATA = mailboot.service

mailboot: mailboot.in
	$(do_substitution) < $(srcdir)/$< > $@
	chmod +x $@

mailboot.service: mailboot.service.in
	$(do_substitution) < $(srcdir)/$< > $@

do_substitution = $(SED) \
	-e 's,[@]bindir[@],$(bindir),g' \
	-e 's,[@]PACKAGE[@],$(PACKAGE),g' \
	-e 's,[@]VERSION[@],$(VERSION),g'

check: mailboot
	./mailboot -p

#install-exec-hook: mailboot.service
#	install -dm755 $(DESTDIR)$(systemdunitdir)
#	install -m644 mailboot.service $(DESTDIR)$(systemdunitdir)/mailboot.service

dist-hook:
	rm -f $(distdir)/TODO
