scl
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-scl.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-scl)

Install Sofware Collections for and CentOS.
Applying this role to other types of operating systems will simply "skip" the job.

Context
-------
This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/robertdebock.github.io/artifacts/scl.png "Dependency")

Requirements
------------

Access to a repository containing packages, likely on the internet.

Role Variables
--------------

None known.

Dependencies
------------

Use this role to prepare your system:

- robertdebock.bootstrap

Download the dependencies by issuing this command:
```
ansible-galaxy install --role-file requirements.yml
```

Compatibility
-------------

This role has been tested against the following distributions and Ansible version:

|distribution|ansible 2.3|ansible 2.4|ansible 2.5|
|------------|-----------|-----------|-----------|
|centos-6|yes|yes|yes|
|centos-7|yes|yes|yes|

Example Playbook
----------------

```
---
- hosts: servers
  become: yes

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.scl

  tasks:
    - name: install package from scl
      package:
        name: python27-python-pip
        state: present    
```

Install this role using `galaxy install robertdebock.scl`.

License
-------

Apache License, Version 2.0

Author Information
------------------

Robert de Bock <robert@meinit.nl>
