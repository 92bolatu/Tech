![nginx logo](http://wiki.nginx.org/local/nginx-logo.png =200x)

Nginx 
=========
------------------------------------------------
nginx [engine x] is an HTTP and reverse proxy server, as well as a mail proxy server.
## Links

- <http://nginx.org/>
- <http://nginx.org/packages/>
- <http://wiki.nginx.org/>

## Install Nginx
**CentOS 7**

	//通过yum安装的nginx会自动注册服务，比编译安装要好用很多
	
	# sudo rpm -Uvh http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm 
	# yum install nginx
	# yum info nginx

**Mac**

	$ brew install nginx
	$ brew info nginx
    
## Nginx Command

	启动服务 $ nginx
	测试配置 $ nginx -t
	停止服务 $ nginx -s stop
	重载配置 $ nginx -s reload
	
## Nginx Config
**配置文件路径**  
	
	可能在以下位置
	$ /etc/nginx/nginx.conf
	$ /usr/local/etc/nginx/nginx.conf
	
**配置文件说明**

    # 运行用户
    user  nginx;
    # 进程数量，建议和cpu挂钩
    worker_processes  1;
    # 全局错误日志及PID文件
    error_log  /var/log/nginx/error.log warn;
    pid        /var/run/nginx.pid;
    
    # 连接数上限
    events {
        worker_connections  1024;
    }
    
    #设定http服务器
    http {
        # 配置mime类型
        include       /etc/nginx/mime.types;
        default_type  application/octet-stream;
        # 日志格式
        log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
                          '$status $body_bytes_sent "$http_referer" '
                          '"$http_user_agent" "$http_x_forwarded_for"';
    
        # 访问日志                      
        access_log  /var/log/nginx/access.log  main;
    
        sendfile        on;
        #tcp_nopush     on;
    
        keepalive_timeout  65;
    
        #gzip  on;
    
        # 在此位置插入配置文件
        # include /etc/nginx/conf.d/*.conf;
    
        # 站点 1
        server {
            # 开启文件目录
            autoindex    on;
            # 文件的确切大小
            autoindex_exact_size off;
            # 时间显示
            autoindex_localtime on;
    
            listen       80;
            server_name  localhost;
    
            #charset koi8-r;
            #access_log  /var/log/nginx/log/host.access.log  main;
    
            location / {
                root   /usr/share/nginx/html;
                index  index.html index.htm;
            }
    
            # [虚拟目录] 父级目录
            # /vp1/ 的父目录是root值
            # http://localhost/vp1/bc.html
            # /usr/share/nginx/test/b/vp1/bc.html
            
            location /vp1/ {
                root /usr/share/nginx/test/b/;
            }   
    
            # [虚拟目录] 绝对路径  
            # /vp2/ 就是 alias 的值
            # http://localhost/vp2/a1.html
            # /usr/share/nginx/test/a/a1.html
            
            location /vp2/ {
                alias /usr/share/nginx/test/a/;
            }  
    
            # redirect server error pages to the static page /50x.html
            error_page   500 502 503 504  /50x.html;
            location = /50x.html {
                root   /usr/share/nginx/html;
            }
        }
    
        # 站点 2
        server {
            listen       8002;
            # 直接定义网站更目录
            root /usr/share/nginx/server2;
        }
    }
    




-----------------------
_Cassandra 2014-07-15_
