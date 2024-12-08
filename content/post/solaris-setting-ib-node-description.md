---
title: "Setting the InfiniBand (IB) Node Description on Solaris"
date: 2012-10-07T12:00:00Z
draft: false
tags: ["Solaris", "InfiniBand", "Networking"]
categories: ["Tech"]
---

In Solaris, configuring the InfiniBand (IB) node description can make your network easier to manage by assigning meaningful names to nodes. This guide explains how to set the IB node description.

---

View the current IB node description

```bash
$ set_nodedesc.sh
```

You can set the IB node description to whatever you want using the -N option with set_nodedesc.sh.

```bash
$ set_nodedesc.sh -N 'something'
```

You can reference the [man page](https://docs.oracle.com/cd/E86824_01/html/E54764/set-nodedesc-sh-1m.html) for the set_nodedesc.sh command to see the full command reference.