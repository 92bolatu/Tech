![mariadb logo](https://mariadb.org/static/generated/images/v2/ice_logo-5dcea9e47b780ff52f75c3c3304d54827f56211e.png =100x100)

MariaDB
=======
------------------
An enhanced, drop-in replacement for MySQL.

## Links

- <https://mariadb.org/>

## Install
**CentOS 7**

	# yum install mariadb mariadb-server 
	# systemctl start mariadb 
	# systemctl stop mariadb
	# systemctl restart mariadb
	
**Mac**

	$ brew install mariadb 
	$ mysql.server start
    $ mysql.server stop
    $ mysql.server restart
	
## Config	
     
     # mysql_secure_installation 
     # mysql -p  
     # mysql -u root -p
     
	//查看用户表的数据信息
	$ MariaDB [(none)]> SELECT host,user,password from mysql.user; 

	//修改用户表的数据，开启远程登录
	$ MariaDB [(none)]> GRANT ALL PRIVILEGES ON *.* TO 'root'@'%'IDENTIFIED BY '123456' WITH GRANT OPTION; 
	
-----------------------
_Cassandra 2014-07-16_	