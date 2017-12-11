[![Build Status](https://travis-ci.org/cjsteel/ansible-role-pass.svg?branch=master)](https://travis-ci.org/cjsteel/ansible-role-pass)
[![Galaxy Role](https://img.shields.io/badge/ansible--galaxy-pass-blue.svg)](https://galaxy.ansible.com/cjsteel/pass/)


ansible-role-pass
====

[pass](http://www.passwordstore.org) is a very simple password store that keeps passwords inside gpg encrypted files inside a simple directory tree. The pass utility provides a series of commands for manipulating the password store, allowing the user to add, remove, edit, synchronize, generate, and manipulate passwords.

## Notes

The gpg key passphrase can be found on the controller in `/tmp/passwordfile`

Requirements
------------

The `pwgen` package is used to generate passwords and must be available in the repositories. On Redhat and Centos you can add `epel-release` to `pass_packages` or remove `pwgen` from the list.

Role Variables
--------------

```
pass_version: 1.6.5
pass_gpg_key: AFBA32A6
pass_git_remote: git@github.com:user/repo
pass_packages:
    - tree
    - git
    - make
    - pwgen
```

Example Playbook
----------------

```
- hosts: servers
  roles:
    - lbischof.pass
```

## References

* [how-to-ultimately-trust-a-public-key-non-interactively.html](https://blog.tersmitten.nl/how-to-ultimately-trust-a-public-key-non-interactively.html)

License
-------

MIT
