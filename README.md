# irods-devenv4micros
This is my iRODS development environment for my microservice implementation. Setup the host addresses in the inventory.yml and than run the playbook.

**NOT FOR PRODUCTION USE**

# requirements
- 2 servers Ubuntu 20.04 LTS needed (1 iCAT + 1 Resource)
- at least 4GB RAM (>better)
- at least 30GB Storage
- servers should reach each other / be in the same network

## ansible
to run this playbook you need the [postgres community module](https://docs.ansible.com/ansible/latest/collections/community/postgresql/postgresql_db_module.html#ansible-collections-community-postgresql-postgresql-db-module)
to install: `ansible-galaxy collection install community.postgresql`
# usage
enter ip to inventory group for example appserver
```
[appserver]
192.168.10.3
```

to run installation:
`ansible-playbook -i inventory -K main.yml` -K stands for prompt become-root password. If no ssh-copy-id was executed before you may add `-k` for connection password too.

