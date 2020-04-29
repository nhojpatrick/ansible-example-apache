# Ansible Example of Apache

## Requirements

  * Vagrant v2.2.7 (may work with any v2.x)
  * VirtualBox v6.1.6 (may work with any v6.x)

## Tested Combinations

The following have been tested, other combinations might work;

- Vagrant v2.2.7 + VirtualBox v6.1.6 + CentOS 7

## Quick Start

Simple as, ` vagrant up`, and a new vm will be created, with 3 websites hosted.

You will need to and the following lines in your host/local hosts file.
```
127.0.0.1 alpha.example.tld
127.0.0.1 bravo.example.tld
```

Then in your browser visit any of these url's.

  - http://localhost:8181/index.html
  - http://alpha.example.tld:8181/index.html
  - http://bravo.example.tld:8181/index.html

The source for these is under the `www` directory and is copied into the vm when the ansible playbook runs. So live update do not currently work.

## Notes

The files `setup_*.yaml` are used as a work around to install the latest version of ansible, including git so that ansible galaxy can install from github.

This setup uses a patch version of the ansible galaxy role 'geerlingguy.apache'. The patch means only tasks that require `become`, instead of running the whole galaxy role with `become`.

  - Patched Version https://github.com/nhojpatrick/geerlingguy_ansible-role-apache/tree/setup-needs-become
  - Origional Version https://github.com/geerlingguy/ansible-role-apache
