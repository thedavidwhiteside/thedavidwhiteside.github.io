---
title: "SPARC OK Prompt Command Reference"
date: 2011-08-07T12:00:00Z
draft: false
tags: ["Solaris", "SPARC", "OK Prompt", "Reference"]
categories: ["Tech"]
---

Maybe you don’t care about the forth programming language, but if you work on Sparc systems long enough you are going to have to work from the ok prompt.

Here are the essentials commands you must know.

Boot the system normally

```bash
ok> boot
```

Boot the system and allow for discovery of new devices (reconfiguration boot)

```bash
ok> boot -r
```

Boot into Single-User Mode

```bash
ok> boot -s
```

Boot into a ROM, useful if your system isn’t bootable

```bash
ok> boot -F failsafe
```

Boot a global-cluster (suncluster) node into single user non-cluster mode.

```bash
ok> boot -sx
```

List your network adapters, you can then do boot net — install [device path] to boot from the network using the specified interface

```bash
ok> show-nets
```

Useful for determining boot devices and general server components

```bash
ok> show-devs
```

devalias lists the device aliases where nvalias is used to set them permanently

```bash
ok> devalias
ok> nvalias diskname /pathdodevice
```

Used to set environment variables used for the openboot firmware.

```bash
ok> printenv
ok> setenv
```

(from the OS shell you can use #eeprom auto-boot?=true, for example to set boot environment variables)

shutdown, reboot, etc

```bash
ok> power-off
ok> reset-all
```