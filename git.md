![git logo](http://git-scm.com/images/logo@2x.png =120x)

Git
===
-------------------------
## Link
- [Git官网](http://git-scm.com/)

- [Git Documentation](http://git-scm.com/doc)


- [廖雪峰Git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)

- [GitLab](https://about.gitlab.com/)



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
	# git commit -a -m "push 2 remote"

**忽略文件**	

	# touch .gitignore
	# vi .gitignore

**查看状态**
	
	#git status
	
### remote

git-remote - Manage set of tracked repositories

<http://git-scm.com/docs/git-remote>

	# git remote [-v | --verbose]
	$ git remote -v
	
	# git remote add <name> <url>
	$ git remote add origin git@192.168.1.109:lwt/tech.git
	$ git remote add gitlan git@192.168.1.12:liuwentao/tech.git
	
	# git remote rename <old> <new>
	$ git remote rename gitlan gitlanwiki
	
	# git remote remove <name>
	$ git remote remove gitlan
	$ git remote rm gitlan
	
	# git push [-u | --set-upstream] [name] [branch]
	$ git push -u origin master	
	$ git push (to defult via -u)
    $ git push gitlan [master]
    $ git push origin && git push wiki
    

	# git pull [options] [<repository> [<refspec>...]]
	$ git pull gitlan	 

