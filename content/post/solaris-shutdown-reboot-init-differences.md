---
title: "Solaris Shutdown, Reboot, Init, and Halt Command Differences"
date: 2012-05-07T12:00:00Z
draft: false
tags: ["Solaris", "Commands", "Unix"]
categories: ["Tech"]
---

The init and shutdown commands cleanly shutdown the system by running the shutdown rc scripts.

The advantage of shutdown is that you can set a shutdown delay and warning message.

halt and reboot are not as clean, no shutdown rc scripts are run so applications will not be brought down clean, I generally do not use these commands unless its a last resort.

```bash
$ init   # runs the shutdown scripts in /etc/rc*
$ init 0 # shutdown (on sparc it takes it to the ok prompt)
$ init s # single user mode
$ init 5 # shutdown
$ init 6 # reboot
```

```bash
$ shutdown # runs the shutdown scripts in /etc/rc*, prints message warning users
$ shutdown -y -g 0
$ shutdown -y -i 0 # shutdown to ok prompt
$ shutdown -y -i S # single user mode
$ shutdown -y -i 5 # shutdown
$ shutdown -y -i 6 # reboot
```

```bash
$ sync; sync; halt # (ungraceful shutdown, use sync;sync;halt)
```

```bash
$ sync; sync; reboot # (ungraceful reboot. Always run sync;sync;reboot. The prefered method is using init.)
$ sync; sync; reboot -- -r  # reconfiguration reboot
$ sync; sync; reboot -- -s # reboot into single usermode
```