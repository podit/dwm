podit's dwm 6.2 fork - https://git.suckless.org/dwm

TODO: implement monitor switching correctly for holdbar, currently switching monitor hangs, presumably an issue with showselmon or possibly pertag patches:wq

for use with the [ly display manager](https://github.com/nullgemm/ly), copy `dwm.desktop` to `/usr/share/xsessions/`

create a bash script at `~/.config/startup` to launch background processes

relies on:
  - kitty
  - st
  - mpd

use [my configuration of dwmblocks](https://github.com/podit/dwmblocks) to display system status info and date/time in the bar

----------------------------
dwm - dynamic window manager
============================
dwm is an extremely fast, small, and dynamic window manager for X.


Requirements
------------
In order to build dwm you need the Xlib header files.


Installation
------------
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

    make clean install


Running dwm
-----------
Add the following line to your .xinitrc to start dwm using startx:

    exec dwm

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm


Configuration
-------------
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.
