Ansible Role GitBucket
=========

An ansible role installs [takezoe/gitbucket](takezoe/gitbucket) without servlet container on CentOS/Ubuntu.
This role deploys minimum configration for GitBucket.

Requirements
------------

None.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

- [geerlingguy.java](https://galaxy.ansible.com/list#/roles/439)

Example Playbook
----------------

```yml
- hosts: servers
  roles:
     - { role: distkloc.gitbucket, gitbucket_host: gitbucket.example.com, gitbucket_port: 80  }
```

License
-------

BSD

