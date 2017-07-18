Role Name
=========

A simple role to manage [EncFS](https://github.com/vgough/encfs) using Ansible.

Requirements
------------

* Ansible 2.2+
* A secret that you want to use as a key.

Role Variables
--------------

*encfs* - absolute location of the directory you want exposed as an ecrypted mount point

*encfs_user* - user to run EncFS process as

*encfs_group* - group of user to run EncFS process as

*passphrase_fetch_cmd* - command that, when executed, provides a passphrase as a string

Example Playbook
----------------

For example:

    - hosts: servers
      roles:
         - { role: rorygibson.encfs, encfs: /var/sensistive-data, passphrase_fetch_cmd: "echo 'MY SECRET'" }

License
-------

Public domain.

Author Information
------------------

Rory Gibson - @rorygibson
