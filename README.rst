========
MAILBOOT
========

INTRODUCTION
============

Once upon a time, a computer reboot. Again. And again. And again.

Whereas a lot of computers reboot and we don't care, few should not reboot
without notifying someone.

*MAILBOOT* is a small program (and systemd service unit) used to send an email
when a computer boot (or reboot), providing useful informations and setupable
in less than 1min.

FAQ
===

Why do not use cron?
--------------------
I started with a cron line. But after workarounded the basic missing feature of
customizing the mail subject in my cron daemon (fcron) in using mail command,
I was borred by being able to send interesting information in one sh line.
So I decided to find another solution.

How to install?
---------------
::

  $ ./autogen.sh
  $ ./configure
  $ make install
  $ /usr/local/bin/mailboot

What you cannot do with mailboot?
-----------------------------------
The coffee.


DEPENDENCIES
============

- Bash [#]_
- Systemd [#]_


RELEASES
========
You can download *MAILBOOT* release tarballs on my ftp: [#]_.


SOURCES
=======
*MAILBOOT* sources are available on github [#]_.


LICENSE
=======
*MAILBOOT* is licensied under the term of GPL v2 [#]_.


AUTHOR
======
*MAILBOOT* was started by Sébastien Luttringer in July 2013.


LINKS
=====
.. [#] http://www.gnu.org/software/bash/
.. [#] http://www.freedesktop.org/wiki/Software/systemd/
.. [#] http://ftp.seblu.net/softs/mailboot/
.. [#] https://github.com/seblu/rebootmail/
.. [#] http://www.gnu.org/licenses/gpl-2.0.html