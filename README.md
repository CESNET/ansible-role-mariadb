# ansible-role-mariadb

Ansible galaxy role cesnet.mariadb that installs and configures MariaDB.

## Requirements


## Role variables
* mariadb_root_password - Password for root user
* databases_to_create - List of databases which will be created
* databases_to_remove - List of databases which will be removed
* users_to_create - Structure of user's login and password
    * Example of structure: 
        ```
        users_to_create:
          - login: user1
            password: password1
          - login: user2
            password: password2
        ```
* users_to_remove - List of users which will be removed
* users_privileges - Structure od user's login and list of privileges
    * Example of structure: 
        ```
        users_privileges:
          - login: user1
            privileges:
              - "dbname1.*:ALL"
              - "dbname2.*:ALL"
          - login: user2
            privileges:
              - "dbname1.*:ALL"
        ```
* master - Information if host is master or slave
* replication_enabled - Information if replication is enabled or not
* replication_cluster_name - Name of cluster
* replication_hosts - List of replication hosts ip's 
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
    - cesmet.mariadb
```