# CGI通用网关接口

## CGI简介 :

CGI是 : “ 公共网关接口 ”\(Common Gateway Interface\)的简称，是HTTP服务器与其它程序进行“ 交谈 ”的一种工具，其程序须运行在网络服务器上。

公共网关接口（Common Gateway Interface，CGI）是Web 服务器运行时外部程序的规范，按CGI 编写的程序可以扩展服务器功能。

CGI 应用程序能与浏览器进行交互，还可通过数据API与数据库服务器等外部数据源进行通信，从数据库服务器中获取数据。

格式化为HTML文档后，发送给浏览器，也可以将从浏览器获得的数据放到数据库中。

几乎所有服务器都支持CGI，可用任何语言编写CGI，包括流行的C、C ++、Java、VB 和Delphi 等。

CGI是一段程序，它运行在Server上，提供同客户端 Html页面的接口。

CGI分为**标准CGI** 和 **间接CGI** :

标准CGI : 使用命令行参数或环境变量表示服务器的详细请求，服务器与浏览器通信采用标准输入输出方式。

间接CGI \( 缓冲CGI \): 在CGI程序和CGI接口之间插入一个缓冲程序，缓冲程序与CGI接口间用标准输入输出进行通信

### CGI的功能：

通常情况下CGI程序被用来解释处理来自表单的输入信息，在服务器产生相应的处理，并将相应的信息反馈给浏览器。

CGI程序使网页具有交互功能。

### CGI处理步骤：

1. 通过Internet把用户请求送到服务器
2. 服务器接收用户请求并交给CGI程序处理
3. CGI程序把处理结果传送给服务器
4. 服务器把结果送回到用户

## CGI编程

CGI可以用任何一种语言编写，只要这种语言具有**标准输入**、**输出**和**环境变量**。

1.CGI程序的输出：

CGI程序中的标准输出是经过重定向了的。CGI程序并不会在服务器上产生任何的输出内容，而是被重定向到客户浏览器。这样，如果编写一个C的CGI程序的时候，把一个HTML文档输出到它的stdout上，这个HTML文档会被在客户端的浏览器中显示出来。这也是CGI程序的一个基本原理。

2.CGI程序第一行输出的内容必须指定Content-Type如：

"Content-Type:text/html"

这个输出作为HTML的文件头。因为CGI不仅可以像浏览器输出HTML文本，而且可以输出图像，声音之类的东西,http服务器向远程发送文件时要说明文件类型。

3.两个重要的CGI环境变量

* QUERY-STRING：GET方法表单输入的数据，URL中间号后的内容。
* CONTENT-LENGTH：POST方法输入的数据的字节数。

CGI编程示例：

