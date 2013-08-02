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

EXTRA_DIST = mailboot.in mailboot.service.in PKGBUILD.in

CLEANFILES = mailboot mailboot.service PKGBUILD

bin_SCRIPTS = mailboot
noinst_SCRIPTS = PKGBUILD
dist_doc_DATA = README.rst COPYRIGHT LICENSE AUTHORS
systemdunit_DATA = mailboot.service
dist_sysconf_DATA = mailboot.conf

mailboot: mailboot.in
	$(do_substitution) < $(srcdir)/$< > $@
	chmod +x $@

mailboot.service: mailboot.service.in
	$(do_substitution) < $(srcdir)/$< > $@

PKGBUILD: PKGBUILD.in
	$(do_substitution) < $(srcdir)/$< > $@

do_substitution = $(SED) \
	-e 's,[@]bindir[@],$(bindir),g' \
	-e 's,[@]sysconfdir[@],$(sysconfdir),g' \
	-e 's,[@]VERSION[@],$(VERSION),g'

check: mailboot
	./mailboot -p

arch: PKGBUILD
	makepkg -f

dist-hook:
	rm -f $(distdir)/TODO
