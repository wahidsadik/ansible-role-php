[![Build Status](https://travis-ci.org/wahidsadik/ansible-role-php.svg?branch=master)](https://travis-ci.org/wahidsadik/ansible-role-php)
[![Galaxy](https://img.shields.io/badge/galaxy-ansible--role--php-green.svg)](https://galaxy.ansible.com/wahidsadik/ansible-role-php)

Role Name
=========

An Ansible role to install PHP and (optionally) integration with Apache2 and MySQL.

The role also installs dependencies to enable Laravel.


The role is available on Ansible Galaxy: [https://galaxy.ansible.com/wahidsadik/ansible-role-php](https://galaxy.ansible.com/wahidsadik/ansible-role-php).

To add this role from Ansible Galaxy, run: `ansible-galaxy install wahidsadik.ansible-role-php`.

To add this from your Ansible `requirements.yml`, add this to the file:

    src: wahidsadik.ansible-role-php

Scope
-----
Works with Ubuntu 14.04.
Does not work with Ubuntu 16.04, as PHP 7 is must.


Requirements
------------
The `remote_user` needs to have `sudo` access or be `root` equivalent user.

Role Variables
--------------

The role defines the following variables in `defaults/main.yml`:

Variable name|Default value|Comment
-------------|-------------|-------
`www_user` | `deployer` | -
`www_group` | `www-data` | -
`integrate_with_apache` | `true` | Needs Apache2
`integrate_with_mysql` | `false` | Needs MySQL

Users must pass the following parameters (i.e. variables):

- None


Dependencies
------------

When

- `integrate_with_apache` is `true`, it is expected that Apache2 is installed on the machine.
- `integrate_with_mysql` is `true`, it is expected that MySQL is installed on the machine.

Example Playbook
----------------

Example 1: Simplest example with minimum variable passing

    - hosts: servers
      remote_user: root
      roles:
         - wahidsadik.ansible-role-php

Example 2: With sudo and minimum variable passing

    - hosts: servers
      remote_user: deployer
      become: true
      become_method: sudo
      roles:
      - wahidsadik.ansible-role-php

Example 3: Overriding additional variables

    - hosts: servers
      remote_user: deployer
      become: true
      become_method: sudo
      roles:
      - {
          role: wahidsadik.ansible-role-php,
          www_user: myuser,
          www_root: /var/web,
          integrate_with_apache: true,
          integrate_with_mysql: true
        }

License
-------

MIT

Author Information
------------------

Wahid Sadik. More at: [https://wahidsadik.github.io](https://wahidsadik.github.io).
