ansible-roles_sysbench-mongodb
=========

Installs and configures [sysbench-mongodb](https://github.com/tmcallaghan/sysbench-mongodb).

Role Variables
--------------

You will want to hack on the variables in defaults/main.yml to fit your liking. Things you will most likely want to change are:

```yaml
---
# defaults file for ansible_roles-sysbench-mongodb

# username for test to log in as
sysbench-mongodb_username: xxx

# password for test to log in as
sysbench-mongodb_password: yyy

# host for test to connec to
sysbench-mongodb_host: localhost

# port for test to connect to
sysbench-mongodb_port: 27017

# database name to use
sysbench-mongodb_database: sbtest

# size of documents per collection
sysbench-mongodb_number_of_docs_per_collection: 100000000

# number of collections
sysbench-mongodb_number_of_collections: 16


```

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
  - { role: ansible-roles_sysbench-mongodb }
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

Running the test
----------------

This role doesn't run the test, only prepare the environment for running the tests easily. To run the test itself on the server(s) where the test is installed do:
```bash
$>su - root
$>cd sysbench
$>./run.simple.bash
```

License
-------

BSD

Author Information
------------------
[Twitter](http://www.twitter.com/kennygorman)

[Github](https://github.com/kgorman)
