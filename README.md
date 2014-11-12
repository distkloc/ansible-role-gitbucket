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

#### Which version of GitBucket to deploy

[Releases · takezoe/gitbucket](takezoe/gitbucket/releases)

```yml
# vars/main.yml
gitbucket_version: 2.5
```

#### Specify GitBucket URL

GitBucket URL is `http://[gitbucket_host]:[gitbucket_port]/[gitbucket_prefix]`

```yml
# vars/main.yml
gitbucket_host: localhost
gitbucket_port: 8080
gitbucket_prefix: ""
```

#### GitBucket data directory

```yml
# defaults/main.yml
gitbucket_home: /var/lib/gitbucket
```

#### Paths for downloaded gitbucket.war

```yml
# defaults/main.yml
gitbucket_dir: /usr/share/gitbucket
gitbucket_war_dir: "{{ gitbucket_dir }}/lib"
gitbucket_war_file: "{{ gitbucket_war_dir }}/gitbucket.war"
```

#### GitBucket log directory

```yml
# defaults/main.yml
gitbucket_log_dir: /var/log/gitbucket
```

#### JVM option used when starting GitBucket

```yml
# defaults/main.yml
gitbucket_jvm_opts: -Dmail.smtp.starttls.enable=true
```

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

