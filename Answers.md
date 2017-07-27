##step1：安装Node.js

**1、下载安装包:**

下载地址：https://nodejs.org/en/download/，根据自己电脑的配置下载相应的windows64位安装包，下载完成后，进行安装。

**2、检查是否安装成功**

安装完成后，打开命令行窗口，检查是否安装成功，如下图所示，键入node -v出现node.js的版本，键入npm -v出现npm的版本，说明两者均已安装成功。

![这里写图片描述](http://img.blog.csdn.net/20170726143819545?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvc2luYXRfMjAxNzczMjc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

**3、配置环境变量**

由于我的电脑之前安装过node.js，所以需要检测一下是否配置了环境变量，打开命令行，输入命令“path”，输出结果中可以看到环境变量已经包含了E:\nodejs\

![这里写图片描述](http://img.blog.csdn.net/20170726150516068?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvc2luYXRfMjAxNzczMjc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

**4、创建一个应用**

在创建应用“Hello World”前，先了解一下node.js应用由哪几部分组成：

- 引入required模块：我们可以使用 require 指令来载入 Node.js 模块。
- 创建服务器：服务器可以监听客户端的请求。
- 接收请求与响应请求：服务器很容易创建，客户端可以使用浏览器或终端发送 HTTP 请求，服务器接收请求后返回响应数据。

下面开始创建node.js应用：

**（1）引入require模块**

我们使用 require 指令来载入 http 模块，并将实例化的 HTTP 赋值给变量 http，实例如下:

```
	var http = require("http");
```

**（2）创建服务器**

接下来我们使用http.creatServer()方法创建服务器，并使用listen()方法绑定8080端口。函数通过request,response参数来接收和响应数据。实例如下：

<pre>
var http = require('http');

http.createServer(function (request, response) {
	// 发送 HTTP 头部 
	// HTTP 状态值: 200 : OK
	// 内容类型: text/plain
	response.writeHead(200, {'Content-Type': 'text/plain'});

	// 发送响应数据 "Hello World"
	response.end('Hello World\n');
}).listen(8080);

// 终端打印如下信息
console.log('Server running at http://127.0.0.1:8080/');
</pre>

使用node命令执行以上代码，结果如下图：

![这里写图片描述](http://img.blog.csdn.net/20170726161415770?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvc2luYXRfMjAxNzczMjc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

打开浏览器访问http://localhost:8080/，可以看到写着"Hello World"的网页，如下图：

![这里写图片描述](http://img.blog.csdn.net/20170726161611482?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvc2luYXRfMjAxNzczMjc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)


##**step2：安装react**

**1、安装react**

https://facebook.github.io/react/docs/installation.html是下载react的官方网站，我是在阮一峰的github上面下载的，里面还包括了很多demo，下载解压后看到bulid文件夹，可以直接引入使用。

**2、构建开发环境**

接着就使用react创建一个应用，当然，除了直接引入react之外，也可以直接使用 BootCDN 的 React CDN 库，在这里我们已经下载了react，所以直接引入。代码如下：


	<!DOCTYPE html>
	<html>
 	 <head>
    	<meta charset="UTF-8" />
    	<title>React!</title>
    	<script src="E:/nodejs/step2/build/react.js"></script>
    	<script src="E:/nodejs/step2/build/react-dom.js"></script>
    	<script src="E:/nodejs/step2/build/browser.min.js"></script>
  	</head>
  	<body>
   	 <div id="example"></div>
    	<script type="text/babel">
    	ReactDOM.render(
        <h1>Hello, world!</h1>,
        document.getElementById('example')
      );
   	 </script>
  	</body>
	</html>


结果如下：

![这里写图片描述](http://img.blog.csdn.net/20170726211002682?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvc2luYXRfMjAxNzczMjc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)


##**step5：总结**

由于自己能力有限，只成功完成了前面两步的任务，后面的任务虽然找到了参考资料，但是对问题本身不是特别理解，所以出现错误没有办法高效解决。总结一下，node.js和react.js之前都没有接触过，这次任务也算是进行了实际操作，中途遇到一些问题自己也找资料查找了，比如react安装过程，以及react的使用方法，除了下载文件之外，还可以直接使用 BootCDN 的 React CDN 库等等。不管结果如何，尽自己所能，学到一些知识就很满足。
