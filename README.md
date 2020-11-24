# Scrnsvr

Yet another X Screensaver/Locker

## Install

Arch Linux: [AUR](https://aur.archlinux.org/packages/scrnsvr) 

Arch Linux (Precompiled version): [AUR](https://aur.archlinux.org/packages/scrnsvr-bin)

To build this yourself:

```bash
git clone https://github.com/koraynilay/scrnsvr
gcc [options] scrnsvr.c -o scrnsvr -lXss -lX11 -lpthread
#to enable full RELRO:
# gcc -g -O0 -Wl,-z,relro,-z,now [options] scrnsvr.c -o scrnsvr -lXss -lX11 -lpthread
```

## Usage:

```
Usage: scrnsvr [OPTIONS]

--help		Shows this help

-t [timeout]	Time in seconds before [saver] gets activated (default: 120)
-a [timeout]	Time in seconds before [locker] gets activated AFTER [saver] has been activated (default: 30)
-s [timeout]	Time in seconds before [blanker] gets activated (default: 180)
-r [saver]	(REQUIRED) Screensaver (e.g. an xscreensaver module)
-l [locker]	(REQUIRED) Program that locks your screen
-b [blanker]	(REQUIRED) Program that blanks/sets your screen off

-w [list]	Space-separated case-insensitive list of windows titles which inhibit the screensaver (added to: youtube vlc mpv vimeo 'picture in picture')
-n		Disables 'Saving in ~n secs' notifications
-c [notifier]	Command used to send notifications (if -n is NOT specified) (not uses different levels)
-c1 [notifier]	Command used to send notifications when there is 1 second left(if -n is NOT specified)
-c2 [notifier]	Command used to send notifications when there is 2 second left(if -n is NOT specified)
-c3 [notifier]	Command used to send notifications when there is 3 second left(if -n is NOT specified)
-c4 [notifier]	Command used to send notifications when there is 4 second left(if -n is NOT specified)
-c5 [notifier]	Command used to send notifications when there is 5 second left(if -n is NOT specified)
-x		Executes until the loop (without entering it) and exits
-v		Prints selected options (even if defaulted)
-d		Shows debug info (Use -D,-u,-U for more levels of debugging)
```

