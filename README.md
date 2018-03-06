scl
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-scl.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-scl)

Install Sofware Collections for and CentOS.
Applying this role to other types of operating systems will simply "skip" the job.

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
