[![Build Status](https://travis-ci.org/wahidsadik/ansible-role-php.svg?branch=master)](https://travis-ci.org/wahidsadik/ansible-role-php)

Role Name
=========

An Ansible role to install PHP and integration with Apache2 (or nginx TBD).

The role is available on Ansible Galaxy: [https://galaxy.ansible.com/wahidsadik/ansible-role-php](https://galaxy.ansible.com/wahidsadik/ansible-role-php).

To add this role from Ansible Galaxy, run: `ansible-galaxy install wahidsadik.ansible-role-php`.

To add this from your Ansible `requirements.yml`, add this to the file:

    src: wahidsadik.ansible-role-php


Requirements
------------

Assumes `mysql` is installed when `integrate_with_mysql` is `true`.
Assumes `apache2` is installed when `integrate_with_apache` is `true`.
Assumes `nginx` is installed when `integrate_with_nginx` is `true`. (TBD)

Role Variables
--------------

The role defines the following variables in `defaults/main.yml`:

    www_user: deployer
    www_group: www-data
    integrate_with_apache: false
    integrate_with_nginx: not supported yet
    integrate_with_mysql: false

Dependencies
------------

The role depends on the following roles:

- item 1
- item 2

(When sudo is needed)
The `remote_user` used run this role should be able change permission of directories and files usually owned by `root`. Hence, you will probably need to `sudo` to successfully run use this role. See examples for more details.

Example Playbook
----------------

Show examples of:

- With simplest possible variables
- With non-root user and in simplest possible variables
- With non-root user with full (and if needed other combinations) variable sets

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.ansible-role-php, integrate_with_apache: true,  integrate_with_mysql: true}

License
-------

MIT

Author Information
------------------

Wahid Sadik

Repo: [https://github.com/wahidsadik/ansible-role-php](https://github.com/wahidsadik/ansible-role-php).
