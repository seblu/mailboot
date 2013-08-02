========
MAILBOOT
========

INTRODUCTION
============

Once upon a time, a computer reboot. Again. And again. And again.

Whereas a lot of computers reboot and we don't care, few should not reboot
without notifying someone.

**MAILBOOT** is a small program (and systemd service unit) used to send an email
when a computer boot (or reboot), providing useful informations and setupable
in less than 1min.

Why do not use cron?
--------------------
I started with a cron line. But after workarounded the basic missing feature of
customizing the mail subject in my cron daemon (fcron) in using mail command,
I was borred by being able to send interesting information in one sh line.
So I decided to find another solution. Here we are.


What you cannot do with mailboot?
-----------------------------------
The coffee.


HOW TO USE IT
=============
To print the mail::

  $ mailboot -p

To send the mail::

  $ mailboot -s

To send the mail at reboot::

  $ systemctl enable mailboot.service


.. caution::
**A working mail forwarder is expected on your system.
The sendmail command must be functionnal!**


DEPENDENCIES
============
- Bash [#]_
- Systemd [#]_
- sysvinit-tools
- Sed


INSTALL
=======

Using autotools
---------------
::

  $ ./autogen.sh
  $ ./configure
  $ make install
  $ /usr/local/bin/mailboot

Using Archlinux packages
------------------------
An Archlinux package is provided with the source tree and you can create your
package with the following commands:

::

  $ ./autogen.sh
  $ ./configure
  $ make
  $ makepkg
  $ pacman -U mailboot-*-1-any.pkg.tar.xz

You can find the last version of mailboot into AUR [#]_.


RELEASES
========
You can download **MAILBOOT** release tarballs on my ftp: [#]_.


SOURCES
=======
**MAILBOOT** sources are available on github [#]_.


LICENSE
=======
**MAILBOOT** is licensied under the term of GPL v2 [#]_.


AUTHOR
======
**MAILBOOT** was started by Sébastien Luttringer in July 2013.


LINKS
=====
.. [#] http://www.gnu.org/software/bash/
.. [#] http://www.freedesktop.org/wiki/Software/systemd/
.. [#] http://ftp.seblu.net/softs/mailboot/
.. [#] https://aur.archlinux.org/packages/mailboot/
.. [#] https://github.com/seblu/mailboot/
.. [#] http://www.gnu.org/licenses/gpl-2.0.html
