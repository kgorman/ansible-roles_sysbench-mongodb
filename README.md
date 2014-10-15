ansible-roles_sysbench-mongodb
=========

Installs and configures [sysbench-mongodb](https://github.com/tmcallaghan/sysbench-mongodb).

Role Variables
--------------

You will want to hack on the variables in defaults/main.yml to fit your liking. Things you will most likely want to change are:

```yaml
# The port for mongodb server
mongodb_port: 9005

# The directory prefix where the database files would be stored
mongodb_datadir_prefix: /data/mongodb/

#TokuMX cache size
mongodb_cache_size: 99000M

# The password for admin user
mongodb_admin_pass: xxx

# The password for admin user
mongodb_admin_user: yyy

```

It's generally recommended to set this to about 80%-90% of main memory on a dedicated DB box.

Install
-------
[See here](https://galaxy.ansible.com/intro)

Example Playbook
----------------

To use this simply setup a YAML file for running:

```yaml
$>cat test.yml
---
- hosts: mongoservers
  roles:
  - { role: ansible-roles_tokumx-install }
```

```yaml
$>cat hosts.txt
[mongoservers]
0.0.0.0
```

and execute like:
```bash
$>ansible-playbook -i hosts.txt test.yml
```

Testing and Requirements
------------------------
This role is tested on Rackspace [onMetal High I/O](http://www.rackspace.com/cloud/servers/onmetal/) servers with Centos 7.

```
uname -a | awk '{print $3}'
3.10.0-123.el7.x86_64
```

License
-------

BSD

Author Information
------------------
[Twitter](http://www.twitter.com/kennygorman)

[Github](https://github.com/kgorman)
