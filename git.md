![git logo](http://git-scm.com/images/logo@2x.png)

Git
===
-------------------------

## Link

- [Git官网](http://git-scm.com/)

- [Git Documentation](http://git-scm.com/docs)


- [廖雪峰Git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)

- [Git命令教程](http://www.cnblogs.com/newpanderking/p/4005698.html)

- [GitLab](https://about.gitlab.com/)

## Line

- 工作区 >> commit >> 本地仓库 >> push >> 远程仓库

- 工作区 << 本地仓库 << pull << 远程仓库


### Git

**初始化仓库**

	# cd ~/develop/noobject/java 6 db2
	# git init

**添加文件**
	
	# git add mariadb-java-client-1.2.0.jar
	# git add src
	# git add .	

### commit

	$ git commit -m "inited"
	$ git commit -a -m "(-a mean add all changed <no add/del> files to commit)"
	$ git commit -a -m this-the-commit-content

**查看状态**

	
	#git status
### delete

	
	# rm <file>	 // 直接删除		
	
	# git rm <file> // 或者通过git删除 	
	
	# git commit -m "工作区缺少的文件会被认定为从仓库删除" // 提交变更
	
	
### gitignore 
	
A text file named **.gitignore** suppresses accidental versioning of files and paths matching the specified patterns.
	
	*.log
	build/
	temp-*
	
Lists all ignored files in this project
	
	$ git ls-files --other
	
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
	
	# git push [-u | --set-upstream] [name] [branch][-f | --force]
	$ git push -u origin master	
	$ git push (to defult via -u)
    $ git push gitlan [master]
    $ git push github master -f
    $ git push origin && git push wiki
    
	# git pull [options] [<repository> [<refspec>...]]
	$ git pull gitlan	

### 删除本地仓库

脱离git管理或者需要重新初始化git仓库时就需要删除本地的git仓库

删除仓库下的**.git**目录即可
	 
	# ll -a
	# rm -fr .git

