Firewalld 
==========
------------------------------
## Link

[Redhat Security Guide](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/Security_Guide/sec-Using_Firewalls.html#sec-Introduction_to_firewalld)

[FirewallD](https://fedoraproject.org/wiki/FirewallD/zh-cn)

http://www.tuicool.com/articles/vMr6Vj

## systemctl

	# systemctl start firewalld
	# systemctl stop firewalld
	# systemctl restart firewalld
	# systemctl status firewalld
	
## firewall-cmd	

**查看命令**

	// 查看防火墙状态
	firewall-cmd --state

	// 查看活动区域
	firewall-cmd --get-active-zones

	// 查看活动服务
	firewall-cmd --get-service

	// 查看自动加载的服务
	firewall-cmd --get-service --permanent
**端口操作**
	
一般情况下只对public区域操作就可以应付一般问题了
	
	// 添加端口
	firewall-cmd --permanent --zone=public --add-port=8080-8081/tcp
 
    // 列出端口
	firewall-cmd --permanent --zone=public --list-ports 
	
    // 移除端口
	firewall-cmd --permanent --zone=public --remove-port=8080-8081/tcp
	
	//重载入配置
	firewall-cmd --reload
	
----------------------------
*Cassandra 2015-07-18*	