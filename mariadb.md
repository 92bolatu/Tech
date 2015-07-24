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
	
## Command Line Client

完整详细的操作方法可以通过 **# mysql -?** 和 **MariaDB [db]> ?** 查看

完整的在线说明<https://mariadb.com/kb/en/mariadb/mysql-command-line-client/>

**常用操作**

	//连接到服务器，省略的参数用默认值
	# mysql -h 192.168.1.12 -P 3306 -u root -p
	
	// 一般命令Sql命令分号结尾	
	MariaDB [db]> show databases;
	MariaDB [db]> select now();
	
	// 文档方式显示搜索结果(类似于json) \G
	MariaDB [db]> show databases \G;
	
	// 输出结果时，按 q 可终止输出的结果
	MariaDB [db]> q
	
	// 取消当前输入的命令
	MariaDB [db]> select id, from
               -> \c
    
    // 使用编辑器编写sql
    MariaDB [db]> \e;
    MariaDB [db]> edit;
    
    // 退出
    MariaDB [db]> exit
    MariaDB [db]> quit
    MariaDB [db]> \q
	
	
-----------------------
_Cassandra 2014-07-24_	