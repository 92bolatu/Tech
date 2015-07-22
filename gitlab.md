![gitlab logo](https://about.gitlab.com/images/downloads/logo.svg =100x)

GitLab
======
---------------------------------------------------------
## Links
[https://about.gitlab.com/](https://about.gitlab.com/)

## Install

**删除git用户**

	# cat /etc/passwd
	# cat /etc/passwd | grep git

**安装依赖**
 	
 	sudo yum install curl openssh-server
	sudo systemctl enable sshd
	sudo systemctl start sshd
	sudo yum install postfix
	sudo systemctl enable postfix
	sudo systemctl start postfix
	sudo firewall-cmd --permanent --add-service=http
	sudo systemctl reload firewalld
	
**安装GitLab**
	
	# rpm -vih gitlab-7.6.2_omnibus.5.3.0.ci.1-1.el7.x86_64.rpm

**配置GitLab**		
	
	# gitlab-ctl reconfigure
	
**浏览器登录**

	http://192.168.1.109

	Username: root 

	Password: 5iveL!fe	

**运行状态**

	# gitlab-ctl status