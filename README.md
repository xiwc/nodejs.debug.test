# Nodejs调试
> http://blog.csdn.net/zhaoweitco/article/details/12677481  

1、全局安装node-inspector

$ `npm install -g node-inspector`

等待安装完成！


2、测试是否安装成功？

$  `node-inspector`

出现如下内容，安装成功！

Node Inspector v0.5.0
   info  - socket.io started
Visit `http://127.0.0.1:8080/debug?port=5858` to start debugging  

如果不成功，轻重复多次进行安装。（网络问题造成安装不成功）


3、进行debug调试。

1) 运行node 调试模式

node提供了两种debug模式运行：  
`node --debug[=port] filename`   
（这种方式，其实就是在指定的端口（默认为 5858）监听远程调试连接）  
`node --debug-brk[=port] filename`   
（这种方式在监听的同时，会在代码执行的时候，强制断点在第一行，这样有个好处就是：可以debug到node内部的是如何运行的）


这里采用第二种方式运行： 

$ `node --debug-brk  app.js`


2) 新建一个连接，启动 node-inspector

$ `node-inspector`

出现如下：

Node Inspector v0.5.0
   info  - socket.io started
Visit http://127.0.0.1:8080/debug?port=5858 to start debugging.

3) 浏览器中调试输入:
>  `http://127.0.0.1:8080/debug?port=5858`
