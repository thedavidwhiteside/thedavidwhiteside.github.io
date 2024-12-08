---
title: "Simple Tool to Create Throw-Away Python Virtual Environments"
date: 2024-12-07T12:00:00Z
draft: false
tags: ["Python", "Virtual Environments", "Programming", "Linux"]
categories: ["Tech"]
---

Managing Python dependencies in isolated environments is a common practice in software development. But what if you need a quick, temporary virtual environment that you can discard after use? Here’s a simple tool and workflow to create throw-away Python virtual environments.

---

### **The Problem**

While Python’s built-in `venv` or tools like `virtualenv` are excellent for managing environments, they require setup and cleanup. For quick experiments or isolated dependency installations, this process can feel cumbersome.

---

### **The Solution** - tempyenv

You can use a simple shell script to automate the creation of throw-away virtual environments.

Simply install and use [tempyenv](https://github.com/outbit/tempyenv)

```bash
$ python -m pip install tempyenv
$ tempyenv
(tempyenv) is setting up your virtual environment...hold tight
Virtual environment created at /var/folders/4b/dnp21z017cg_rbgfdtzclqlm0000gn/T/tmpacwjkg5z/venv
Virtual environment loading from /var/folders/4b/dnp21z017cg_rbgfdtzclqlm0000gn/T/tmpacwjkg5z/venv
(tempyenv)(venv) $ pip install whatever_package_you_need
(tempyenv)(venv) $ exit # or ctrl-d
```