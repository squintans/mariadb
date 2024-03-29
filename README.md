Ansible Role: MariaDB
=====================

This role install and secure MariaDB from official repo with mysql_root_password: "password".

Version of MariaDB can be edit on defaults/main.yml "mysql_version".

Versions availables at: http://yum.mariadb.org/
- 10.0
- 10.1
- 10.2
- 10.3
- 10.4
- ..

Requirements
------------

This Ansible playbook is meant to be run on a FRESH never used server, virtual machine or container.

Role Variables
--------------

**defaults/main.yml:***
```
# MariaDB
mariadb_mariadb_version: '10.4'

# Mysql root
mariadb_mysql_root_password: 'password'
mariadb_mysql_user: 'root'
```

**vars/:***
```
Debian.yml
RedHat.yml
```

Role Templates
==============

None.

Dependencies
------------

None.

Example Playbook
----------------

**Example with prompt:**
```
- hosts: "{{ vm }}"
  gather_facts: True

  vars_prompt:
    - name: "vm"
      prompt: "VM"
      private: no

  roles:
    - { role: squintans.mariadb }
```

Playbook Call
=============
```
ansible-playbook -i inventory.yml play.yml
```

License
-------

GPLv2

Author Information
------------------
This role was created in 2019 by Serafín Quintáns - [@squintans](http://www.linkedin.com/in/serafin-quintans/)