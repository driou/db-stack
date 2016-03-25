# DB Stack
Docker compose with 3 node Mariadb Galera Cluster 

### FROM
https://github.com/scottpgallagher/galeramaster
https://github.com/scottpgallagher/galeranode
https://github.com/scottpgallagher/galera-compose

Remastered with Debian / MariaDB 10.1 instead of 5.5 and without Consul 
		
image build in repository

#### Problem

`mysql.sh` not creating database access.
