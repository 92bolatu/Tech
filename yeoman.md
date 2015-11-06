Yeoman
======
[http://yeoman.io/]()

[http://yeoman.io/learning/index.html]()


    // 安装yeoman和相关依赖
	$ npm install -g yo bower grunt-cli gulp
	
	// 安装生成器 angular-fullstack
	$ npm install -g generator-angular-fullstack
	
	// 执行yo配置项目
	$ yo
	
	
添加依赖 ： /hicds-www/package.json
	

	{
		"name": "hicds-www",
		"version": "0.0.0",
		"main": "server/app.js",
		"dependencies": {
			"body-parser": "~1.5.0",
			"express-session": "~1.0.2",
			"http-proxy": "^1.11.1",
 			...
			}
		...	
	}	

修改配置 ： /hicds-www/server/config/environment/development.js

	'use strict';

	// Development specific configuration
	// ==================================
	module.exports = {
    	// MongoDB connection options
    	mongo: {
        	uri: 'mongodb://localhost/hicdswww-dev'
    	},
    	proxy: {
        	path: 'http://localhost:8080'
        	//path: 'http://localhost:8008'
    	},
    	seedDB: true
	};	
	
	
添加代理 ： /hicds-www/dist/server/config/express.js	
	
	'use strict';

	...
		
	var httpProxy = require('http-proxy');

	module.exports = function (app) {
    	var env = app.get('env');
    	app.set('views', config.root + '/server/views');
	    app.engine('html', require('ejs').renderFile);
    	app.set('view engine', 'html');
    	app.use(compression());

    	var proxy = httpProxy.createProxyServer({});

    	// TODO api server config
    	app.use('/api', function (req, res) {
        	proxy.web(req, res, {target: config.proxy.path})
    	});
    	
    	...
    	
    };


**node 插件目录**

--------------------

+ /usr/local/lib/node_modules/generator-angular-fullstack

+ /usr/local/lib/node_modules/generator-webapp

+ /usr/local/lib/node_modules/generator-angular


###yeoman project init

```
cassandra@localhost:~/project-www$ [yo]
? 'Allo Cassandra! What would you like to do? [Angular Fullstack]

Make sure you are in the directory you want to scaffold into.
This generator can also be run with: yo angular-fullstack


     _-----_
    |       |
    |--(o)--|   .--------------------------.
   `---------´  |    Welcome to Yeoman,    |
    ( _´U`_ )   |   ladies and gentlemen!  |
    /___A___\   '__________________________'
     |  ~  |
   __'.___.'__
 ´   `  |° ´ Y `

Out of the box I create an AngularJS app with an Express server.

# Client

? What would you like to write scripts with? [JavaScript]
? Would you like to use Javascript ES6 in your client by preprocessing it with Babel? [No]
? What would you like to write markup with? [HTML]
? What would you like to write stylesheets with? [CSS]
? What Angular router would you like to use? [ngRoute]
? Would you like to include Bootstrap? [Yes]
? Would you like to include UI Bootstrap? [Yes]

# Server

? Would you like to use mongoDB with Mongoose for data modeling? [No]
You're using the fantastic NgComponent generator.

Initializing yo-rc.json configuration.

Creating files....

```


	

