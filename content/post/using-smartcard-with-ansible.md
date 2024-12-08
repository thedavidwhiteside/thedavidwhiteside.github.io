---
title: "Using a Smartcard (PIV or CAC) with Ansible"
date: 2018-03-07T12:00:00Z
draft: false
tags: ["Ansible", "Smartcard", "PIV", "CAC", "Linux"]
categories: ["Tech"]
---

As part of the Ansible 2.12 release, pkcs11/smartcards are now supported by Ansible. Now you can use smartcards and other devices that support pkcs11 (Yubikey) to configure systems with Ansible.

Setup your middleware for pkcs11, below is how to install opensc on a Mac using homebrew.

```bash
$ brew install opensc
```

To use pkcs11 for authentication set the ANSIBLE_PKCS11_PROVIDER environment variable

```bash
$ export ANSIBLE_PKCS11_PROVIDER=/usr/local/lib/opensc-pkcs11.so
$ ansible-playbook -u USERNAME -b -k -K PLAYBOOK.yml --connection=ssh
SSH password: << Enter your PKCS11 Pin for your smartcard
SUDO password[defaults to SSH password]: << Enter your user account password for sudo
```

For more details see the [feature PR](https://github.com/ansible/ansible/pull/32829).