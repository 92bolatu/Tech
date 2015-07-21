[]

Git
===
-------------------------
## Link
[Git官网](http://git-scm.com/)

[廖雪峰Git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)

[GitLab](https://about.gitlab.com/)

## Git

**初始化仓库**

	# cd ~/develop/noobject/java 6 db2
	# git init

**添加文件**
	
	# git add mariadb-java-client-1.2.0.jar
	# git add src
	# git add *	

**本地提交**	

	# git commit -m "init"

**忽略文件**	

	# touch .gitignore
	# vi .gitignore

**查看状态**
	
	#git status
	
**远程仓库**

	#git remote
	#git remote -v
	
	# git remote add origin git@192.168.1.109:lwt/tech.git
	# git push -u origin master	
	# git pull origin

	# git remote add gitlan git@192.168.1.12:liuwentao/tech.git
	# git push -u gitlan master	
	# git pull gitlan

gitlan