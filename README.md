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

The following will ensure that */var/sensitive-data* provides a plain-text view of encrypted data contained in */var/sensitive-data_encrypted*. The passphrase will be 'MY SECRET'.

    - hosts: servers
      roles:
         - { role: rorygibson.encfs, encfs: /var/sensitive-data, passphrase_fetch_cmd: "echo 'MY SECRET'" }

And this will use a passphrase retrieved from the metadata service of the hosting environment.

    - hosts: servers
      roles:
         - { role: rorygibson.encfs, encfs: /var/sensitive-data, passphrase_fetch_cmd: "curl --silent http://metadata-server/my-passphrase-key" }

License
-------

Public domain.

Author Information
------------------

Rory Gibson - @rorygibson
