# ansible-role-mariadb

Ansible galaxy role cesnet.mariadb that installs and configures MariaDB.

## Requirements


## Role variables
* mariadb_root_password - Password for root user
* mariadb_databases_to_create - List of databases which will be created
* mariadb_databases_to_remove - List of databases which will be removed
* mariadb_users_to_create - Structure of user's login and password, and optional host and database privileges
    * Example of structure: 
        ```
        mariadb_users_to_create:
          - login: user1
            password: password1
            host: "%"
            privileges: "dbname1.*:ALL"
          - login: user2
            password: password2
        ```
* mariadb_users_to_remove - List of users which will be removed
* mariadb_users_privileges - Structure od user's login and list of privileges
    * Example of structure: 
        ```
        mariadb_users_privileges:
          - login: user1
            privileges:
              - "dbname1.*:ALL"
              - "dbname2.*:ALL"
          - login: user2
            privileges:
              - "dbname1.*:ALL"
        ```
* mariadb_is_master - Information if host is master or slave
* mariadb_replication_enabled - Information if replication is enabled or not
* mariadb_replication_cluster_name - Name of cluster
* mariadb_replication_hosts - List of replication hosts ip's 
## Available tags
* install
* scheme - Create/Remove database and run scripts
* configuration
* start
* stop

## Example playbook
```
- hosts: all
  remote_user: root
  vars:
  roles:
    - cesnet.mariadb
```
