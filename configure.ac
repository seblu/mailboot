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

AC_INIT([mailboot], [3], [seblu@seblu.net])

AM_INIT_AUTOMAKE([foreign dist-xz no-dist-gzip])

AC_CONFIG_FILES([
	Makefile
])

AC_ARG_WITH([systemdunitdir],
	AS_HELP_STRING([--with-systemdunitdir=DIR], [Systemd unit directory]),
	[], [with_systemdunitdir=${libdir}/systemd/system]
)
AC_SUBST([systemdunitdir], [$with_systemdunitdir])


AC_CHECK_PROG([BASH], [bash], true, false)
AC_PROG_SED

AC_OUTPUT
