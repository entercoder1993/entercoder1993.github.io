---
title: Python网络爬虫开发实战
date: 2018-09-11 22:24:32
tags: [Python,Spider]
categories: Note
---

# Python网络爬虫开发实战

## 一、开发环境配置

### 1.1 Python3

* 相关链接
  * 官方网站：[https://www.python.org](https://www.python.org)
  * 下载地址：[https://www.python.org/downloads](https://www.python.org/downloads)
  * 第三方库：[https://pypi.org](https://pypi.org)
  * 官方文档：[https://docs.python.org/3](https://docs.python.org/3) [中文文档](http://docspy3zh.readthedocs.io/en/latest/index.html)
  * 中文教程：
    * [菜鸟教程](http://www.runoob.com/python3/python3-tutorial.html)
    * [廖雪峰Python3教程](https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)

### 1.2 请求库的安装

#### Request的安装

* 相关链接
  * GitHub：[https://github.com/requests/requests](https://github.com/requests/requests)
  * PyPI：[https://pypi.org/project/requests/](https://pypi.org/project/requests/)
  * 官方文档：[http://docs.python-requests.org/en/master/](http://docs.python-requests.org/en/master/)
  * 中文文档：[http://cn.python-requests.org/zh_CN/latest/](http://cn.python-requests.org/zh_CN/latest/)

#### Selenium的安装

* 相关链接
  * 官方网站：[https://www.seleniumhq.org/](https://www.seleniumhq.org/)
  * GitHub：[https://github.com/SeleniumHQ/Selenium](https://github.com/SeleniumHQ/Selenium)
  * PyPI：[https://pypi.org/project/selenium/](https://pypi.org/project/selenium/)
  * 官方文档：[http://selenium-python.readthedocs.io/](http://selenium-python.readthedocs.io/)
  * 中文文档：[http://selenium-python-zh.readthedocs.io](http://selenium-python-zh.readthedocs.io)

#### ChromeDriver的安装

* 相关链接
  * 官方地址：[http://chromedriver.chromium.org/](http://chromedriver.chromium.org/)
  * 下载地址：https://chromedriver.storage.googleapis.com/index.html?path=2.40/（需根据Chrome的版本下载对应的ChromeDriver）
* 环境变量配置：
  * Windows：将chromedriver.exe文件拖到Python的Scripts目录下即可。
  * Linux和Mac下
    * 将文件移动到`/usr/bin`目录下`suod mv chromedriver /usr/bin`
    * 或者将ChromeDriver配置到`$PATH export PATH="$PATH:/usr/local/chromedriver"`

#### GeckoDriver的安装

* 相关链接
  * Github：[https://github.com/mozilla/geckodriver](https://github.com/mozilla/geckodriver)
  * 下载地址：[https://github.com/mozilla/geckodriver/releases](https://github.com/mozilla/geckodriver/releases)

#### PhantomJS的安装

* 相关链接
  * 官方网站：http://phantomjs.org
  * 官方文档：http://phantomjs.org/quick-start.html
  * 下载地址：http://phantomjs.org/download.html
  * API接口说明：http://phantomjs.org/api/command-line.html

#### aiohttp的安装

* 相关链接
  * 官方文档：https://docs.aiohttp.org/en/stable/
  * GitHub：https://github.com/aio-libs/aiohttp
  * PyPI：https://pypi.org/project/aiohttp/

### 1.3 解析库的安装

#### lxml的安装

* 相关链接
  * 官方网站：https://lxml.de/
  * GitHub：https://github.com/lxml/lxml
  * PyPI：https://pypi.org/project/lxml/

#### Beautiful Soup4的安装

* 相关链接
  * 官方网站：https://www.crummy.com/software/BeautifulSoup/bs4/doc/
  * 中文文档：https://www.crummy.com/software/BeautifulSoup/bs4/doc.zh/
  * PyPI：https://pypi.org/project/beautifulsoup4/

#### pyquery的安装

- 相关链接
  - 官方网站：https://pythonhosted.org/pyquery/
  - GitHub：https://github.com/gawel/pyquery/
  - PyPI：https://pypi.org/project/pyquery/

#### tesserocr的安装

- 相关链接
  - tesserocr GitHub：https://github.com/tesseract-ocr/tesseract
  - tesserocr PyPI：https://pypi.org/project/tesserocr/
  - tesseract 下载地址：https://github.com/tesseract-ocr/tesseract/wiki
  - tesseract GitHub：https://github.com/tesseract-ocr/tesseract
  - tesseract语言包：https://github.com/tesseract-ocr/tessdata
  - tesseract文档：https://github.com/tesseract-ocr/tesseract/wiki/Documentation

### 1.4 数据库的安装

#### MySQL的安装

#### MongoDB的安装

#### Redis的安装

### 1.5 存储库的安装

#### PyMySQL的安装

#### PyMongo的安装

#### redis-py的安装

#### RedisDump的安装

### 1.6 Web库的安装

#### Flask的安装

#### Tornado的安装

### 1.7 App爬取相关的库安装

#### Charles的安装

#### mitmproxy的安装

### 1.8 爬虫框架的安装

#### pyspider的安装

安装：

```python
pip3 install pyspider
```

问题：

Curl is configured to use SSL, but we have not been able to determine which SSL backend it is using.

解决方法：

```bash
sudo pip3 uninstall pycurl
export PYCURL_SSL_LIBRARY=openssl
export LDFLAGS=-L/usr/local/opt/openssl/lib;export CPPFLAGS=-I/usr/local/opt/openssl/include;pip install pycurl --compile --no-cache-dir
```

#### Scrapy的安装

#### Scrapy-Splash的安装

#### Scrapy-Redis的安装

### 1.9 部署库相关的库的安装

#### Docker的安装

* 安装

  ```bash
  $brew cask install docker
  ```

#### Scrapyd的安装

* 安装

  ```bash
  $pip3 install scrapyd
  ```

* 配置

  * 新建配置文件/etc/scrapyd/scrapyd.conf

#### Scrapyd的安装

#### Scrapyd-Client的安装

#### Scrapyd API的安装

#### Scrapyrt的安装

#### Gerapy的安装

## 二、爬虫基础

### 2.1 HTTP基本原理

> **请求**网站并**提取**数据的**自动化**程序

* URI和URL
  * URI全称Uniform Resource Identifier，即统一资源标志符

  * URL全称Universal Resource Locator，即统一资源定位符

  * URL是URI的子集

  * 另一个子类为URN全称Universal Resource Name，即统一资源名称

  * 关系

      ![img](https://ws2.sinaimg.cn/large/006tNc79gy1ft42wp69kxj308704c74c.jpg)

* 超文本(hypertext)，网页就是超文本解析而成的。

* HTTP和HTTPS

  * HTTP全称Hyper Text Transfer Protocol，中文名称:超文本传输协议。是用于从网络传输文本数据到本地浏览器的传送协议，它能保证高效而准确地传送超文本文档。
  * HTTPS全称Hyper Text Transfer Protocol voer Secure  Socket Layer，是以安全为目标的HTTP通道，即HTTP的安全版，HTTP下加入SSL层，简称HTTPS
      * 作用:
          *   建立一个信息安全通道来保证数据传输的安全
          *   确认网站的真实性，凡是使用了HTTPS的网站，都可以通过点击浏览地址栏的锁头标志来查看网站认证之后的真实信息，也可以通过CA机构颁发的安全签章来查询。

* HTTP请求过程

  1. 浏览器向网站所在的服务器发送一个请求
  2. 网站服务器接受到这个请求后进行处理和解析
  3. 返回对应的响应（响应包含页面的源代码等内容）
  4. 传回给浏览器（浏览器对其进行解析，便将网页呈现出来）

  ![img](https://ws2.sinaimg.cn/large/006tNc79ly1ft4s5tla9lj30c204o3yt.jpg)

  5. Chrome浏览器

     ![image-20180710151010965](https://ws2.sinaimg.cn/large/006tNc79ly1ft4s9daqiqj31hb0budj9.jpg)

     * Name：请求的名称，一般会将URL的最后一部分内容当做名称
     * Status：响应的状态码，200代表响应是正常的
     * Type：请求的文档类型
     * Initiator：请求源。用来标记请求是由哪个对象或进程发起的
     * Size：从服务器下载的文件和请求的资源大小。如果从缓存中取得的数据，则该列会像是from cache
     * Time：发起请求到获取响应所用的总时间
     * Waterfall：网络请求的可视化瀑布流

* 请求

  * 请求方法

    * GET
    * POST
    * 区别
      * GET请求中的参数包含在URL里面，数据可以在URL中看到，而POST请求的URL不会包含这些数据，数据都是通过表单形式传输的，会包含在请求体中
      * GET请求提交的数据最多只有1024字节，而POST方式没有限制
    * 其他方法：
      * GET、HEAD、POST、PUT、DELETE、OPTIONS、CONNECT、TRACE等

    | 方法    | 描述                                                         |
    | ------- | ------------------------------------------------------------ |
    | GET     | 请求页面，并返回页面内容                                     |
    | HEAD    | 类似于GET请求，只不过返回的响应中没有具体的内容，用于获取报头 |
    | POST    | 大多用于提交表单或上传文件，数据包含在请求体中               |
    | PUT     | 从客户端向服务器传送的数据取代指定文档中的内容               |
    | DELETE  | 请求服务器删除指定的页面                                     |
    | CONNECT | 把服务器当做跳板，让服务器代替客户端访问其他网页             |
    | OPTIONS | 允许客户端查看服务器的性能                                   |
    | TRACE   | 回显服务器收到的请求，主要用于测试或诊断                     |

  * 请求的网址：即统一资源定位符URL，它可以唯一确定我们想请求的资源

  * 请求头

    * Accept：请求报头域，用于指定客户端可接受哪些类型的信息
    * Accept-Language：制定客户端可接受的语言类型
    * Accept-Encoding：指定客户端可接受的内容编码
    * Host：用于请求资源的主机IP和端口号，其内容为请求URL的原始服务器或网关的位置
    * Cookie：常用复数形式Cookies，这是网站为了辨别用户进行会话跟踪而存储在用户本地的数据。主要功能是维持当前访问会话。
    * Referer：便是请求是从哪个页面发过来的，服务器可以拿到这一信息并做相应的处理，如做来源统计、防盗链处理等。
    * User-Agent：简称UA，它是一个特殊的字符串头，可以使服务器识别客户使用的操作系统及版本、浏览器及版本等信息。在做爬虫时加上此信息，可以伪装为浏览器；如果不加，很可能会被识别为爬虫。
    * Content-Type：也叫互联网媒体类型或者MIME类型，如HTTP协议消息头中，它用来表示具体请求中的媒体类型信息。text\html代表HTML格式，image/gif代表GIF图片，application/json代表JSON类型等。

  * 请求体：登录之前，填写的用户名和密码信息，提交时这些内容就会以表单数据的形式提交给服务器，只有有设置Request Headers中的Content-Type为application/x-www-form-urlencoded时，才会以表单数据的形式提交。

    | Content-Type                      | 提交数据的方式 |
    | --------------------------------- | -------------- |
    | application/x-www-form-urlencoded | 表单数据       |
    | mulitipart/form-data              | 表单文件上传   |
    | application/json                  | 序列化JSON数据 |
    | text/xml                          | XML数据        |

* 响应

  * 响应状态码（Response Status Code）

    ![img](https://ws2.sinaimg.cn/large/006tKfTcgy1ft6aro73clj30is0o4wix.jpg)

    ![img](https://ws4.sinaimg.cn/large/006tKfTcgy1ft6arvf6lcj30in03q74u.jpg)

  * 响应头（Response Headers）

    * Date：标识响应产生的时间
    * Last-Moidfied：指定资源的最后修改时间
    * Content-Encoding：指定响应内容的编码
    * Server：包含服务器的信息，比如名称、版本号等
    * Content-Type：文档类型，指定返回的数据类型是什么就返回什么类型
    * Set-Cookie：设置Cookies。响应头中的Set-Cookie告诉浏览器需要将此内容放在Cooikes中，下次请求携带Cookies请求
    * Expires：指定响应的过期时间，可以使代理服务器或浏览器将加载的内容更新到缓存中。如再次访问时，就可以直接从缓存中加载。

  * 响应体（Response Body）：响应的正文数据都在响应体重，比如请求网页时，它的响应就是网页的HTML代码。爬虫请求网页后，要解析的内容就是响应体。

### 2.2 网页基础

* 网页可以分成三大部分：HTML、CSS和JavaScript

  * HTML（Hyper Text Markup Language，即超文本标记语言）：是用来描述网页的一种协议
  * CSS（Cascading Sytle Sheet，即层叠样式表）：“层叠”是指当在HTML中引用了数个样式文件，并且样式发生冲突时，浏览器能依据层叠顺序处理。“样式”指网页中文字大小、颜色、元素间距、排列等格式
  * JavaScript：简称JS，是一种脚本语言。HTML和CSS配合使用，提供给用户的只是一种静态信息，缺乏交互性。网页里的交互和动画效果，通常都是JavaScript的功劳。它的出现使得用户与信息之间不只是一种浏览与显示的关系，而是实现了一种实时、动态、交互的页面功能。

* 网页的结构

  ```html
  <!-- 定义文档类型 -->
  <!DOCTYPE HTML>
  <html>
      <!-- head标签内定义了一些页面的配置和引用 -->
      <head>
          <!-- 指定网页编码为utf-8 -->
          <meta charset="utf-8">
          <!-- 网页的标题 -->
          <title>This is a Demo</title>
      </head>
      <body>
          <!-- div标签定义了网页中的区块，id是container，id的内容在网页中是唯一的 -->
          <div id="container">
              <!-- class所谓wrapper -->
            <div class="wrapper">
                  <h2>
                      Hello World
                  </h2>
                  <p>
                      Hello,This iis a paragraph.
                  </p>
              </div>
          </div>
      </body>
  </html>
  ```

* 节点树及节点间的关系：在HTML中，所有标签定义的内容都是节点，它们构成了HTML DOM树

  > DOM(Document Object Model)文档对象模型。它定义了访问HTML和XML文档的标准

  * W3C DOM标准被分为3个不同的部分

    1. 核心DOM：针对任何结构化文档的标准模型
    2. XML DOM：针对XML文档的标准模型
    3. HTML DOM：针对HTML文档的标准模型

  * 根据W3C的HTML DOM标准，HTML文档中的所有内容都是节点

    * 整个文档是一个文档节点
    * 每个HTML元素是元素节点
    * HTML元素内的文本是文本节点
    * 每个HTML属性都是属性节点
    * 注释是注释节点

  * 节点树

    ![img](https://ws1.sinaimg.cn/large/006tKfTcly1ftnbc6u3r1j30di078mxt.jpg)

  * 节点树及节点之间的关系

    ![img](https://ws3.sinaimg.cn/large/006tKfTcly1ftnbdr0yg5j30au078aaf.jpg)

* CSS选择器的语法规则

  ![img](https://ws4.sinaimg.cn/large/006tKfTcly1ftnbi5yxaaj30le04c0tf.jpg)


  * 节点树

    ![img](https://ws1.sinaimg.cn/large/006tKfTcly1ftnbc6u3r1j30di078mxt.jpg)

  * 节点树及节点之间的关系

    ![img](https://ws3.sinaimg.cn/large/006tKfTcly1ftnbdr0yg5j30au078aaf.jpg)

* CSS选择器的语法规则

  ![img](https://ws4.sinaimg.cn/large/006tKfTcly1ftnbi5yxaaj30le04c0tf.jpg)

  ![img](https://ws1.sinaimg.cn/large/006tKfTcly1ftnbjot2cdj30ld0n80y2.jpg)

  ![img](https://ws4.sinaimg.cn/large/006tKfTcly1ftnblw5mb1j30lq02wgm4.jpg)

### 2.3 爬虫的基本原理

* 爬虫概述：爬虫就是获取网页并提取和保存信息的自动化程序。
  1. 获取网页：获取网页的源代码，并从源代码中提取想要的信息
  2. 提取信息：分析网页源代码，从中提取我们想要的数据。
     * 正则表达式提取，这是一个万能的方法，但是在构造时比较复杂且易出错。
     * 根据网页节点属性、CSS选择器或XPath来提取网页信息的库：如Beautiful Soup、pyquery、lxml。
  3. 保存数据：可以简单保存为文本或JSON文本，也可以保存到数据库，如MySQL和MongoDB等，也可以保存至远程服务器。
  4. 自动化程序：爬虫可以替代我们来完成爬取工作的自动化程序，他可以在爬取过程中进行各种异常处理、错误重试等操作，以确保爬取持续高效地运行。

* 能抓怎样的数据：HTML源代码、二进制数据、JSON字符串等，只要在浏览器里面可以访问得到，就可以将其抓取下来。

* JavaScript渲染页面

  网页越来越多地采用Ajax、前端模块化工具来构建，整个网页可能都是由JavaScript渲染出来的，原始的HTML代码就是一个空壳。使用urlib或requests请求当前页面时，我们只能得到这个HTML代码，它不会帮助我们去继续加载这个JavaScript文件。

  * 解决方法
    * 分析Ajax接口
    * 使用Selenium、Splash等库实现模拟JavaScript渲染

### 2.4 会话和Cookies

#### 无状态HTTP

HTTP协议对事务处理是没有记忆能力的，即服务器不知道客户端是什么状态。当我们向服务器发送请求后，服务器解析请求，然后返回对应的响应，服务器负责完成这个过程，该过程是完全独立的，服务器不会记录前后状态的变化，缺少状态记录。若后续需要处理前面的信息，则必须重传，这导致需要额外传递一些前面的重复请求，才能获取后续响应。

会话和Cookies可以保持HTTP连接的状态，会话在服务端，Cookies在客户端。浏览器在下次访问网页时会自动附带上Cookies发送给服务器，服务器通过识别Cookies并鉴定出是哪个用户，然后再判断用户是否是登录状态，然后返回对应的响应。

会话和Cookies可以保持HTTP连接的状态，会话在服务端，Cookies在客户端。浏览器在下次访问网页时会自动附带上Cookies发送给服务器，服务器通过识别Cookies并鉴定出是哪个用户，然后再判断用户是否是登录状态，然后返回对应的响应。

* 会话：在Web中，会话对象用来存储特定用户会话所需的属性及配置信息。当用户在应用程序的Web也之间跳转存储在会话对象中的变量将不会丢失，而是在用户会话中一直存在下去。当用户请求来自应用程序的Web页时，如果该用户还没有会话，则Web服务器自动创建一个会话对象。当会话过期或被放弃后，服务器将终止该会话。
* Cookies：Cookies指某些网站为了辨别用户身份、进行会话跟踪而存储在用户本地端上的数据。
  * 会话维持
  * 属性结构
    * Name：Cookies的名称，一旦创建不可更改
    * Value：该Cookies的值。如果值为Unicode字符，需要为字符编码。如果为二进制数据，则需要用BASE64编码
    * Domain：可以访问该Cookie的域名
    * Max Age：Cookie失效的时间，单位为秒，若为正数，则Cookie在Max Age秒之后失效。若为负数，关闭浏览器即失效。
    * Path：该Cookie的使用路径。若设置为/，则本域名下所有页面都可以访问该Cookie
    * Size：Cookie的大小
    * HTTP：Cookie的httponly属性。若为True，则只有在HTTP头中带有此Cookie的信息，而不能通过document.cookie来访问此Cookie
    * Secure：该Cookie是否仅被使用安全协议传输。安全协议有HTTPS和SSL等，在网络上传输数据之间先将数据加密。默认为false
* 常见误区
  * 除非程序通知服务器删除一个会话，否则服务器会一直保留。
  * 关闭浏览器不会导致会话被删除，这就需要服务器为会话设置一个失效时间，当距离客户端上一次使用会话的时间超过这个失效时间时，服务器就可以认为客户端已停止活动，然后才会将会话删除。

### 2.5 代理的基本原理

#### 基本原理

代理实际上是指代理服务器，英文叫作proxy server，他的功能是代理网络用户去取得网络信息。形象地说，它是网络信息的中转站。如果设置了代理服务器，本机不是直接向Web服务器发起请求，而是向代理服务器发出请求，请求会发送给代理服务器，然后代理服务器再发送给Web服务器，接着由代理服务器再把Web服务器返回的响应转发给本机。
<<<<<<< HEAD

* 作用

  * 突破IP访问限制，访问一些平时不能访问的站点
  * 访问一些单位或团体内部资源：比如使用教育网内地址段免费代理服务器，就可以对教育网开放的各类FTP下载上传，以及各类资料查询共享等服务
  * 提高访问速度：通常代理服务器都设置一个较大的硬盘缓冲区，当有外接的信息通过时，同时也将其保存在缓冲区中，当其他用户再访问相同的信息时，则直接由缓冲区中取出信息，传给用户，以提高访问速度。
  * 隐藏真实IP

* 爬虫代理

* 作用

  * 突破IP访问限制，访问一些平时不能访问的站点
  * 访问一些单位或团体内部资源：比如使用教育网内地址段免费代理服务器，就可以对教育网开放的各类FTP下载上传，以及各类资料查询共享等服务
  * 提高访问速度：通常代理服务器都设置一个较大的硬盘缓冲区，当有外接的信息通过时，同时也将其保存在缓冲区中，当其他用户再访问相同的信息时，则直接由缓冲区中取出信息，传给用户，以提高访问速度。
  * 隐藏真实IP

* 爬虫代理

  对于爬虫来说，由于爬虫爬取速度过快，在爬取过程中可能遇到同一个IP访问过于频繁的问题，此时网站就会让我们输入验证码登录后者直接封锁IP。

  使用代理隐藏真实的IP，让服务器以为是代理服务器在请求自己。这样再爬取过程中通过不断更换代理，就不会被封锁。

* 代理分类

  * 根据协议
    * FTP代理服务器：主要用于访问FTP服务器，一般有上传、下载及缓存功能，端口一般为21、2121等
    * HTTP代理服务器：主要用于访问网页，一般有内容过滤和缓存功能，端口一般为80、8080、3128
    * SSL/TLS代理：主要用于访问加密网站，一般有SSL或TLS加密功能（最高支持128位加密强度），端口一般为443
    * RTSP代理：主要用于访问Real流媒体服务器，一般有缓存功能，端口一般为554
    * Telnet代理：主要用于telnet远程控制（黑客入侵计算机时常用语隐藏身份），端口一般为23
    * POP3/SMTP代理：主要用户POP3/SMTP方式收发邮件，一般有缓存功能，端口一般为110/25
    * SOCKS代理：单纯传递数据包，速度快，一般有缓存功能，端口一般为1080
      * SOCKS4：只支持TCP
      * SOCKS5：支持TCP和UDP，还支持各种身份验证机制、服务器域名解析等
  * 根据匿名程度
    * 高度匿名代理：数据包原封不动地转发
    * 普通匿名代理：会在数据包上做一些改动，服务端有可能发现这个是代理服务器，也有一定几率追查到真实IP。代理服务器通常会加入的HTTP头有HTTP_VIA和HTTP_X_FORWARDED_FOR
    * 透明代理：不但改动数据包，还有告诉服务器客户端的真实IP。这种代理除了能用缓存技术提高浏览速度，能将内容过滤提高安全性之外，并无其他显著作用，最常见的例子是内网中的硬件防火墙
    * 间谍代理：指组织或个人创建的用于记录用户传输的数据，然后进行研究、监控等目的的代理服务器

* 常见代理设置

  * 使用网上的免费代理
  * 使用付费代理服务
  * ADSL拨号

## 三、基本库的使用

### 3.1 使用urllib

> [官方文档](https://docs.python.org/3/library/urllib.html)

* 四个模块

  * request：最基本的HTTP请求模块，用来模拟发送请求
  * error：异常处理模块，若出现请求错误，可以捕获这些异常，然后进行重试或其他操作保证程序不会意外终止
  * parse：工具模块，提供URL处理方法，比如拆分、解析、合并等
  * robotparser：识别网站的robots.txt文件

* 发送请求

  * urlopen()

    urllib.request.urlopen(url,data=None,[timeout,]*,cafile=None,capath=None,cadefault=False,context=None)

    ```python
    import urllib.request
    
    response = urllib.request.urlopen('https://www.python.org')
    print(response.read().decode('utf-8'))
    
    # 输出为HTTPResponse类型对象，主要包含read()、readinto()、getheader(name)、getheaders()、fileno()等方法
    # msg、version、status、reason、debuglevel、closed属性等
    print(type(response))
    print(response.status)
    print(response.getheaders())
    print(response.getheader('Server'))
    ```

    * data参数
    * timeout参数
    * 其他参数

  * Request

    ```python
    import urllib.request
    
    request = urllib.request.Request('https://python.org')
    response = urllib.request.urlopen(request)
    print(response.read().decode('utf-8'))
    ```

    依然通过urlopen()方法来发送请求，但是该方法的参数不再是URL。而是一个request类型的对象。这样可以将请求独立成一个对象，也可以灵活地配置参数。

    class urllib.request.Request(url,data=None,headers={},origin_req_host=None,unverifiable=False,method=None)

    * url：用于请求URL，这是必传参数，其他都是可选参数。
    * data：必须传bytes(字节流)类型的参数。如果是字典，可以通过rullib.parse模块里的urlencode()编码。
    * headers：该参数是一个字典，它就是请求头，可以直接构造，也可以通过调用请求实例的add_headers()方法添加。
    * origin_req_host：指的是请求方的host名称或IP地址。
    * unverifiable：表示这个请求是否是无法验证的，默认是False。例如，我们请求一个HTML文档中的图片，但是我们没有自动抓取图像的权限，这时unverifiable的值就是True。
    * method：用来指示请求使用的方法，比如GET、POST和PUT等。

    ```python
    from urllib import request,parse
    
    url = 'http://httpbin.rog/post'
    headers = {
        'User-Agent':'...',
        'Host':'httpbin.org'
    }
    dict = {
        'name':'Germey'
    }
    data = bytes(parse.urlencode(dict),encoding='utf-8')
    req = request.Request(url=urll,data=data,headers=headers,method='POST')
    # 使用add_headers()方法添加
    # req = request.Request(url=urll,data=data,method='POST')
    # req.add_headers('User-Agent','Mozilla/4.0...')
    response = request.urlopen(req)
    print(response.read().decode('utf-8'))
    ```

  * 高级用法

* 处理异常

  * URLError
  * HTTPError

* 解析链接

* 分析Robots协议

### 3.2 使用requests

* 安装

  ```bash
  $pip3 install requests
  ```

* 实例

  ```python
  import  requests
  
  r = requests.get('https://www.baidu.com')
  r.encoding = r.apparent_encoding
  print(type(r))
  print(r.status_code)
  print(type(r.text))
  print(r.text)
  print(r.cookies)
  
  r= requests.post('http://httpbin.org/post')
  r= requests.put('http://httpbin.org/put')
  r= requests.delete('http://httpbin.org/delete')
  r= requests.head('http://httpbin.org/get')
  r= requests.options('http://httpbin.org/get')
  ```

* GET请求

  ```python
  import requests
  
  r = requests.get('http://www.httpbin.org/get')
  print(r.text)
  
  # 添加参数
  data = {
      'name':'germey',
      'age':22
  }
  r = requests.get('http://httpbin.org/get',params=data)
  print(r.text)
  
  # 直接解析返回结果，可以得到一个字典格式的结果
  print(r.json())
  print(type(r.json()))
  ```

  * 抓取知乎发现页标题

    ```python
    import requests
    import re

    headers = {
        'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/68.0.3440.84 Safari/537.36'
    }
    r = requests.get('https://www.zhihu.com/explore',headers=headers)
    pattern = re.compile('explore-feed.*?question_link.*?>(.*?)</a>',re.S)
    titles = re.findall(pattern,r.text)
    print(titles)
    ```

  * 抓取二进制数据

    ```python
    import requests

    r = requests.get('http://github.com/favicon')
    print(r.content)
    with open('pic.jpg','wb') as f:
        f.write(r.content)
    ```

* POST请求

  ```python
  import requests
  
  data = {'name':'germey','age':22}
  # 提交数据到form，说明POST请求成功
  r = requests.post('http://httpbin.org/post',data=data)
  print(r.text)
  ```

* 响应

  ```python
  import requests
  
  headers = {
      'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/68.0.3440.84 Safari/537.36'
  }
  r = requests.get('http://www.jianshu.com',headers=headers)
  print(type(r.status_code),r.status_code)
  # headers属性得到的结果CaseInsensitiveDict
  print(type(r.headers),r.headers)
  # cookies属性得到的结果RequestsCookieJar
  print(type(r.cookies),r.cookies)
  print(type(r.url),r.url)
  print(type(r.history),r.history)
  
  # 内置的状态码查询对象requests.codes
  exit() if not r.status_code == requests.codes.ok else print('successs')
  
  # print('fault') if r.status_code == requests.codes.not_found else exit()
  ```

* 高级用法

  * 文件上传

    ```python
    import requests

    files = {'file':open('favicon.icon','rb')}
    r = requests.post('http://httpbin.org/post',files=files)
    print(r.text)
    print(r.status_code)
    ```

  * Cookies设置

    ```python
    import requests

    r = requests.get('https://www.baidu.com')
    print(r.cookies)

    for key,value in r.cookies.items():
        print(key + '=' + value)

    # 利用Cookies维持登录状态
    import requests

    headers = {
        'Cookie':'......',
        'Host':'www.zhihu.com',
        'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/68.0.3440.84 Safari/537.36'

    }
    r = requests.get('https://www.zhihu.com',headers=headers)
    print(r.text)
    ```

  * 会话维持

    使用Session对象维持会话，可以做到模拟同一个会话二不用担心Cookies的问题。通常用于模拟登录成功后再进行下一步的操作。

    ```python
    import requests

    s = requests.Session()
    s.get('http://httpbin.org/cookies/set/number/123456789')
    r = s.get('http://httpbin.org/cookies')
    print(r.text)
    ```

  * SSL证书验证

    ```python
    import requests
    import logging
    # from requests.packages import urllib3
    # 忽略警告
    # urllib3.disable_warnings()
    # 捕获警告到日志
    logging.captureWarnings(True)
    r = requests.get('https://www.12306.cn',verify=False)
    # 或指定本地证书用作客户端证书
    # ...
    print(r.status_code)
    ```

  * 代理设置

    ```python
    import requests

    #proxies = {
    #    'http':'http://10.10.1.10:3128',
    #    'https':'http://10.10.1.10:1080'
    #}
    proxies = {
        'http':'http://user:password@10.10.1.10:3128/',
    }
    requests.get('https://www.taobao.com',proxies=proxies)
    ```

  * 超时设置

    ```python
    import requests

    # timeout=None则为永久等待，或直接不加参数
    r = requests.get('https://www.taobao.com',timeout = 1)
    print(r.status_code)
    ```

  * 身份认证

    ```python
    import requests

    r = requests.get('http:localhost:5000',auth=('username','password'))
    print(r.status_code)
    ```

* Prepared Requests

  在requests中将请求表示为数据结构，这个数据结构就叫Prepared Requests

  ```python
  from requests import Request,Session
  
  url = 'http://httpbin.org/post'
  data = {
      'name':'germey'
  }
  headers = {
      'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/68.0.3440.84 Safari/537.36'
  }
  s = Session()
  req = Request('POST',url,data=data,headers=headers)
  prepped = s.prepare_request(req)
  r = s.send(prepped)
  print(r.text)
  ```

### 3.3 正则表达式

* 常用匹配规则

  | 模式   | 描述                                                         |
  | ------ | ------------------------------------------------------------ |
  | \w     | 匹配字母、数字及下划线                                       |
  | \W     | 匹配不是字母、数字及下划线的字符                             |
  | \s     | 匹配任意空白字符，等价于[\t\n\r\f]                           |
  | \S     | 匹配任意非空字符                                             |
  | \d     | 匹配任意数字，等价于[0-9]                                    |
  | \D     | 匹配任意非数字字符                                           |
  | \A     | 匹配字符串开头                                               |
  | \Z     | 匹配字符串结尾，若存在换行，只匹配到换行前的结束字符串       |
  | \z     | 匹配字符串结尾，若存在换行，同时还会匹配换行符               |
  | \G     | 匹配最后匹配完成的位置                                       |
  | \n     | 匹配一个换行符                                               |
  | \t     | 匹配一个制表符                                               |
  | ^      | 匹配一行字符串的开头                                         |
  | $      | 匹配一行字符串的结尾                                         |
  | .      | 匹配任意字符，除了换行符，当re.DOTALL标记被指定时，则可以匹配包括换行符的任意字符 |
  | [...]  | 用来表示一组字符串，单独列出，比如[amk]匹配a、m或k           |
  | [^...] | 不在[]中的字符，比如\[^abc]匹配除了a、b、c之外的字符         |
  | *      | 匹配0个或多个表达式                                          |
  | +      | 匹配1个或多个表达式                                          |
  | ?      | 匹配0个或1个前面的正则表达式定义的片段，非贪婪方式           |
  | {n}    | 精确匹配n个前面的正则表达式                                  |
  | {n,m}  | 匹配n到m次由前面正则表达式定义的片段，贪婪方式               |
  | a\|b   | 匹配a或b                                                     |
  | ()     | 匹配括号内的表达式，页表示一个组                             |

* match()

  match()会从字符串的起始位置匹配正则表达式，如果匹配，返回匹配成功的结果；若不匹配，则返回None

  ```python
  import re
  
  content = 'Hello 123 4567 World_This is a Regex Demo'
  print(len(content))
  
  result = re.match('^Hello\s\d\d\d\s\d{4}\s\w{10}',content)
  print(result)
  # group()可以输出匹配到的内容
  print(result.group())
  # span()输出匹配结果在原字符串中的的位置范围，
  print(result.span())
  ```

  * 匹配目标

    可以使用括号()将想要提取的子字符串括起来。()实际上标记了一个表达式的开始和结束位置，被标记的每个子表达式会依次对应每一个分组，调用group()方法传入分组的索引即可获取提取的结果

    ```python
    import re

    result = re.match('^Hello\s(.*?)\sWorld',content)
    print(result)
    print(result.group())
    print(result.group(1))
    print(result.span())
    ```

  * 通用匹配

    ```python
    import re

    # .*可以匹配任意字符
    result = re.match('^Hello.*Demo$',content)
    print(result)
    print(result.group())
    print(result.span())
    ```

  * 贪婪与非贪婪

    ```python
    import re

    # 运行结果只得到7，在贪婪匹配中，.*会匹配尽可能多的字符，\d+代表至少一个数字，
    # 所以.*尽可能的匹配多的字符，因此只留下一个可满足条件的数字7
    result = re.match('^He.*(\d+).*Demo$',content)
    print(result)
    print(result.group(1))

    # .*?是非贪婪匹配，就是尽可能匹配少的字符
    result = re.match('^He.*?(\d+).*Demo$',content)
    print(result)
    print(result.group(1))

    content = 'http://weibo.com/comment/kEraCN'
    result1 = re.match('http.*?comment/(.*?)',comment)
    result2 = re.match('http.*?comment/(.*)',comment)
    print('result1',result1.group(1))
    print('result2',result1.group(2))
    # 运行结果为
    # result1
    # result2 kEraCN
    # .*?没有匹配到任何结果，.*尽量匹配多的内容，因此成功匹配
    ```

  * 修饰符

    ```python
    import re

    content = ''''Hello 1234567 World_This 
    is a Regex Demo'''
    # 运行报错，因为这个正则表达式无法匹配到换行符，所以返回结果None
    # result = re.match('^He.*?(\d+).*?Demo$',content)
    # print((result.group(1)))
    # 添加re.S即可修正此错误，这个修饰符可以匹配包括换行符在内的所有字符
    result = re.match('^He.*?(\d+).*?Demo$',content，re.S)
    print((result.group(1)))
    ```

    | 修饰符 | 描述                                                       |
    | ------ | ---------------------------------------------------------- |
    | re.I   | 使匹配对大小写不敏感                                       |
    | re.L   | 做本地化识别匹配                                           |
    | re.M   | 多行匹配，影响^和$                                         |
    | re.S   | 使.匹配包括换行在内的所有字符                              |
    | re.U   | 根据Unicode字符集解析字符。这个标志影响\w、\W、\b、\B      |
    | re.X   | 该标志通过给予更灵活的格式以便你将正则表达式写得更易于理解 |

  * 转义匹配

    若目标字符串里包含.,，则需要用到转义匹配

    ```python
    import re

    content = '(百度)www.baidu.com'
    result = re.match('\(百度\)www\.baidu\.com',content)
    print(result)
    ```

* search()

  match()方法是从字符串的开头开始匹配的，一旦开头不匹配，name整个匹配就失败了。search()在匹配时会扫描整个字符串，然后返回第一个成功匹配的结果。若搜索完成还未找打，则返回None

  ```python
  import re
  
  content = 'Extra stings Hello 1234567 World_This is a Regex Demo Extra stings'
  result = re.match('Hello.*?(\d+).*?Demo',content)
  print(result)
  # None
  
  result = re.search('Hello.*?(\d+).*?Demo',content)
  print(result)
  ```

  ```python
  import re
  
  html = '''
      <div id="songs-list">
          <h2 class="title">经典老歌</h2>
          <p class="introduction">
              经典老歌列表
          </p>
          <ul id="list" class="list-group">
              <li data-view="2">一路有你</li>
              <li data-view="7">
                  <a>沧海一声笑</a>
              </li>
              <li data-view="4" class="active">
                  <a href="/5.mp3" singer="齐秦">随风往事</a>
              </li>
              <li data-view="6">
                  <a href="/5.mp3" singer="beyond">光辉岁月</a>
              </li>
              <li  data-view="5">
                  <a href="/5.mp3" singer="陈慧琳">记事本</a>
              </li>
              <li  data-view="5">
                  <a href="/.6mp3" singer="邓丽君">但愿人长久</a>
              </li>
          </ul>
      </div>
  '''
  
  result = re.search('<li.*?active.*?singer="(.*?)">(.*?)</a>',html,re.S)
  print(result.group(1),result.group(2))
  
  # 若不加active
  result = re.search('<li.*?singer="(.*?)">(.*?)</a>',html,re.S)
  # 则返回匹配的第一条结果
  ```

* findall()

  findall()会搜索整个字符串，然后返回匹配正则表达式的所有内容，返回的是列表类型

  ```python
  result = re.findall('<li.*?href="(.*?)".*?singer="(.*?)">(.*?)</a>',html,re.S)
  print(type(result))
  for result in result:
      print(result)

  # 返回的列表中的每个元素都是元祖类型，用对应的索引一次取出即可。
  ```

* sub()

  除了使用正则表达式提取信息外，有时候还需要借助它来修改文本。

  ```python
  import re
  
  content = '54aK54yr5oiR54ix5L2g'
  # 第一个参数\d+用来匹配所有的数字，第二个参数为替换成的字符串，第三个参数为原字符串
  content = re.sub('\d+','',content)
  
  # 上面的HTML文本也可以直接使用正则表达式修改之后再进行提取，就会简单很多了
  result = re.sub('<a.*?>|</a>','',html)
  print(result)
  results = re.findall('<li.*?>(.*?)</li>',result,re.S)
  for result in  results:
      print(result.strip())
  ```

* compile()

  compile()可以将正则字符串编译成正则表达式对象，以便在后面的匹配中复用

  ```python
  import re
  
  content1 = '2016-12-15 12:00'
  content2 = '2016-12-17 12:55'
  content3 = '2016-12-22 13:21'
  # 还可以将修饰符传入，这样在search()、findall()方法中就不需要额外传了
  pattern = re.compile('\d{2}:\d{2}')
  result1 = re.sub(pattern,'',content1)
  result2 = re.sub(pattern,'',content2)
  result3 = re.sub(pattern,'',content3)
  print(result1,result2,result3)
  ```

### 3.4 抓取猫眼电影排行

* 目标：提取出猫眼电影TOP100的电影名称、时间、评分、图片等信息，提取的站点URL为[http://maoyan.com/board/4](http://maoyan.com/board/4)，提取结果 会以文件形式保存下来。

* 分析

  * 目标站点：[http://maoyan.com/board/4](http://maoyan.com/board/4)
  * 第二页：[http://maoyan.com/board/4?offset=10](http://maoyan.com/board/4?offset=10)

  1. 抓取首页实现get_one_page(url)

  2. 正则表达式提取：

     ```python
     '\<dd>.*?board-index.*?>(.*?)\</i>.*?data-src="(.*?)".*?name.*?a.*?>(.*?)\</a>.*?"star".*?>(.*?)\</p>.*?"releasetime".*?>(.*?)\</p>.*?"integer".*?>(.*?)\</i>.*?"fraction".*?>(.*?)\</i>.*?\</dd>'
     ```

  3. 写入文件

  4. 分页爬取

  5. 运行代码

* 代码

```python
import requests
import re
from requests.exceptions import RequestException
import json
from multiprocessing import Pool

def get_one_page(url):
    try:
        headers = {
            'User-Agent':'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/67.0.3396.99 Safari/537.36'
        }
        response = requests.get(url,headers=headers)
        if response.status_code == 200:
            return response.text
        return None
    except RequestException:
        return None

def parse_one_page(html):
    pattern = re.compile('<dd>.*?board-index.*?>(.*?)</i>.*?data-src="(.*?)".*?name.*?a.*?>(.*?)</a>.*?"star".*?>(.*?)</p>.*?"releasetime".*?>(.*?)</p>.*?"integer".*?>(.*?)</i>.*?"fraction".*?>(.*?)</i>.*?</dd>',re.S)
    items = re.findall(pattern,html)
    for item in items:
        yield {
            'index':item[0],
            'image':item[1],
            'title':item[2],
            'actor':item[3].strip()[3:],
            'time':item[4].strip()[5:],
            'score':item[5] + item[6]
        }

def write_to_file(content):
    with open('result.txt','a',encoding='utf-8') as f:
        f.write(json.dumps(content,ensure_ascii=False) + '\n')
        f.close()


def main(offset):
    url = 'http://maoyan.com/board/4?offset=' + str(offset)
    html = get_one_page(url)
    for item in parse_one_page(html):
        write_to_file(item)
        print(item)
    # print(html)


if __name__ == '__main__':

    pool = Pool()
    pool.map(main,[i * 10 for i in range(10)])

```

### 练习：抓取豆瓣top250电影排行

```python
import requests
from requests.exceptions import RequestException
import re
import json
from multiprocessing import Pool

def get_one_page(url):
    try:
        headers = {
            'User-Agent':'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/67.0.3396.99 Safari/537.36'
        }
        response = requests.get(url,headers=headers)
        if response.status_code == 200:
            return response.text
        return None
    except RequestException:
        return None

def parse_one_page(html):
    pattern = re.compile('<li>.*?class="">(.*?)</em>.*?"title">(.*?)</span>.*?average">(.*?)</span>.*?inq">(.*?)</span>.*?</li>',re.S)
    items = re.findall(pattern,html)
    for item in items:
        yield {
            'index':item[0],
            'title':item[1],
            'score':item[2],
            'quote':item[3]
        }

def write_to_file(content):
    with open('douban.txt','a',encoding='utf-8') as f:
        f.write(json.dumps(content,ensure_ascii=False) + '\n')
        f.close()

def main(start):
    url = "https://movie.douban.com/top250?start=" + str(start)
    html = get_one_page(url)
    for item in parse_one_page(html):
        # print(item)
        write_to_file(item)

if __name__ == '__main__':
    # for i in range(10):
    #     main(i * 25)
    pool = Pool()
    pool.map(main, [i * 25 for i in range(10)])

```

## 四、解析库的使用

### 4.1 使用XPath

* 常用规则

  | 表达式   | 描述                     |
  | -------- | ------------------------ |
  | nodename | 选取此节点的所有子节点   |
  | /        | 从当前节点选取直接子节点 |
  | //       | 从当前节点选取子孙节点   |
  | .        | 选取当前节点             |
  | ..       | 选取当前节点的父节点     |
  | @        | 选取属性                 |

  栗子：//title[@lang='eng'] —— 代表选择所有名称为title，同时属性lang的值为eng的节点

* 实例

  ```python
  from lxml import etree
  
  text = '''
  <div>
      <ul>
          <li class="item-0"><a href="link1.html">first item</a></li>
          <li class="item-1"><a href="link2.html">second item</a></li>
          <li class="item-inactive"><a href="link3.html">third item</a></li>
          <li class="item-0"><a href="link4.html">fourth item</a></li>
          <li class="item-1"><a href="link5.html">fifth item</a></li>
      </ul>
  <div>
  '''
  
  html = etree.HTML(text)
  # tostring输出结果为bytes类型，这里利用decode()方法将其转成str类型
  result = etree.tostring(html)
  print(result.decode('utf-8'))
  ```

* 所有节点

  我们一般会用//开头的XPath规则来选取所有符合要求的节点。

  ```python
  from lxml import etree
  
  html = etree.HTML(text)
  # 这里的*代表匹配所有节点，即整个HTML文本中的所有节点都会被获取
  result = html.xpath('//*')
  print(result)
  
  html = etree.HTML(text)
  # 这里选取所有li节点，直接在//后加上节点名称即可
  result = html.xpath('//li')
  print(result)
  print(result[0])
  ```

* 子节点

  通过/或//即可查找子节点或子孙节点

  ```python
  from lxml import etree
  
  html = etree.HTML(text)
  # 选择li节点的所有直接a子节点
  result = html.xpath('//li/a')
  print(result[0].text)
  
  html = etree.HTML(text)
  result = html.xpath('//ul//a')
  print(result)
  ```

* 父节点

  通过..可以查找父节点

  ```python
  from lxml import etree
  
  html = etree.HTML(text)
  result = html.xpath('//a[@href="link4.html"]/../@class')
  print(result)
  
  html = etree.HTML(text)
  # 也可以通过parent::获取父节点
  result = html.xpath('//a[@href="link4.html"]/parent::*/@class')
  print(result)
  ```

* 属性匹配

  可以用@符号进行属性过滤

  ```python
  from lxml import etree
  
  html = etree.HTML(text)
  result = html.xpath('//li[@class="item-0"]')
  print(result)
  ```

* 文本获取

  XPath中的text()方法可以获取节点中的文本

  ```python
  # 先选取a节点再获取文本
  html = etree.HTML(text)
  result = html.xpath('//li[@class="item-0"]/a/text()')
  print(result)
  
  # 使用//
  html = etree.HTML(text)
  result = html.xpath('//li[@class="item-0"]//text()')
  print(result)
  
  # 直接用//加text()的方式，可以保证获取到最全面的文本信息，但是可能会夹杂一些换行符等特殊字符
  # 如果想要获取某些特定子孙节点下的所有文本，可以先选取到特定的子孙节点，再调用text()方法获取其内部文本，这样可以保证获取到的结果是整洁的
  ```

* 属性获取

  ```python
  html = etree.HTML(text)
  result = html.xpath('//li/a/@href')
  print(result)
  ```

* 属性多值匹配

  ```python
  from lxml import etree
  
  text = '''
  <li class="li li-first"><a href="link.html">first item</a></li>
  '''
  html = etree.HTML(text)
  result = html.xpath('//li[contains(@class,"li")]/a/text()')
  print(result)
  ```

* 多属性匹配

  需要同时匹配多个属性，可以使用运算符and来连接

  ```python
  from lxml import etree
  
  text = '''
  <li class="li li-first" name="item"><a href="link.html">first item</a></li>
  '''
  
  html = etree.HTML(text)
  result = html.xpath('//li[contains(@class,"li") and @name="item"]/a/text()')
  print(result)
  ```

  | 运算符 | 描述           | 实例               | 返回值                           |
  | ------ | -------------- | ------------------ | -------------------------------- |
  | or     | 或             | age=19 or age=20   | 19-true,21-false                 |
  | and    | 与             | age>19 and age <21 | 20-true,22-false                 |
  | mod    | 除法的余数     | 5 mod 2            | 1                                |
  | \|     | 计算两个节点集 | //book \| //cd     | 返回所有拥有book和cd元素的节点集 |
  | +      | 加法           | 6+4                | 10                               |
  | -      | 减法           | 6-4                | 2                                |
  | *      | 乘法           | 6*4                | 24                               |
  | div    | 除法           | 8 div 4            | 2                                |
  | =      | 等于           | age=19             | 19-true,20-false                 |
  | !=     | 不等于         | age!=19            | 19-false,18-true                 |
  | <      | 小于           | age<19             | 19-false,18-false                |
  | <=     | 小于或等于     | age<=19            | 19-true,20-false                 |
  | >      | 大于           | age>19             | 19-false,21-true                 |
  | >=     | 大于或等于     | age>=19            | 19-true,18-false                 |

* 按序选择

  ```python
  from lxml import etree
  
  text = '''
  <div>
      <ul>
          <li class="item-0"><a href="link1.html">first item</a></li>
          <li class="item-1"><a href="link2.html">second item</a></li>
          <li class="item-inactive"><a href="link3.html">third item</a></li>
          <li class="item-0"><a href="link4.html">fourth item</a></li>
          <li class="item-1"><a href="link5.html">fifth item</a></li>
      </ul>
  <div>
  '''
  
  html = etree.HTML(text)
  result = html.xpath('//li[1]/a/text()')
  print(result)
  result = html.xpath('//li[last()]/a/text()')
  print(result)
  result = html.xpath('//li[last()-2]/a/text()')
  print(result)
  result = html.xpath('//li[position()<3]/a/text()')
  print(result)
  ```

* 节点轴选择

  ```python
  from lxml import etree
  
  text = '''
  <div>
      <ul>
          <li class="item-0"><a href="link1.html">first item</a></li>
          <li class="item-1"><a href="link2.html">second item</a></li>
          <li class="item-inactive"><a href="link3.html">third item</a></li>
          <li class="item-0"><a href="link4.html">fourth item</a></li>
          <li class="item-1"><a href="link5.html">fifth item</a></li>
      </ul>
  <div>
  '''
  html = etree.HTML(text)
  # ancestor可以获取祖先节点，其后需要跟两个冒号，*匹配所有节点
  result = html.xpath('//li[1]/ancestor::*')
  print(result)
  result = html.xpath('//li[1]/ancestor::div')
  print(result)
  # attribute获取所有属性值
  result = html.xpath('//li[1]/attribute::*')
  print(result)
  # child获取所有直接子节点
  result = html.xpath('//li[1]/child::a[@href="link1.html"]')
  print(result)
  # descendant可以获取所有子孙节点
  result = html.xpath('//li[1]/descendant::span')
  print(result)
  # following可以获取当前节点之后的所有节点，可以使用索引
  result = html.xpath('//li[1]/following::*[2]')
  print(result)
  # following-sibling可以获取当前节点之后的所有同级节点
  result = html.xpath('//li[1]/following-sibling::*')
  print(result)
  ```

  > [更多参考](http://www.w3school.com.cn/xpath/index.asp)

### 4.2 使用BeautifulSoup

Beautiful  Soup就是Python的一个HTML或XML的解析库，可以用它来方便地从网页中提取数据

* 基本用法

  ```python
  html = '''
  <!DOCTYPE html>
  <html lang="en">
  
  <head>
      <title>Document</title>
  </head>
  
  <body>
      <p class="title" name="dromouse">
          <b>The Dormouse's story</b>
      </p>
      <p class="story">
          Once upon a time there were three little sisters;and their names were
          <a href="http://example.com/elsie" class="sister" id="link1">
              <!-- Elsie -->
          </a>,
          <a href="http://example.com/lacie" class="sister" id="link2">Lacie</a> and
          <a href="http://example.com/tillie" class="sister" id="link2">Tillie</a>; and they lived at the bottom of a well.</p>
      </p>
      <p class="story">
          ...
      </p>
  </html>
  '''
  
  from bs4 import BeautifulSoup
  soup = BeautifulSoup(html,'lxml')
  print(soup.prettify())
  print(soup.title.string)
  ```

* 节点选择器

  * 选择元素

    ```python
    print(soup.title)
    print(type(soup.title))
    print(soup.title.string)
    print(soup.head)
    # 当存在多个节点，这种选择方式只会选择第一个匹配的节点
    print(soup.p)
    ```

  * 提取信息

    1. 获取名称
    2. 获取属性
    3. 获取内容

    ```python
    print(soup.title.name)

    print(soup.p.attrs)
    print(soup.p.attrs['name'])

    print(soup.p.b.string)
    ```

  * 嵌套选择

    ```python
    print(soup.head.title)
    print(type(soup.head.title))
    print(soup.head.title.string)
    ```

  * 关联选择 —— 先选中某一节点元素，然后以它为基准再选择它的子节点、父节点、兄弟节点等

    * 子节点和孙节点

* 方法选择器

* CSS选择器

### 4.3 使用pyquery

## 五、数据存储

### 5.1 文件存储

#### TXT存储

* 实例：保存知乎上“发现”页面的“热门话题”部分，将其问题和答案统一保存成文本形式

* 使用requests获取网页源代码，使用pyquery解析库解析

  ```python
  import requests
  from pyquery import PyQuery as pq
  
  url = 'https://www.zhihu.com/explore'
  headers = {
    'User-Agent':'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/67.0.3396.99 Safari/537.36'
  }
  html = requests.get(url,headers=headers).text
  file_html = open('explore.html','a',encoding='utf-8')
  file_html.write(html)
  file_html.close()
  doc = pq(html)
  items = doc('.explore-tab .feed-item').items()
  for item in items:
    question = item.find('h2').text()
    author = item.find('.author-link-line').text()
    answer = pq(item.find('.content').html()).text()
    file = open('explore.txt','a',encoding='utf-8')
    file.write('\n'.join([question,author,answer]))
    file.write('\n' + '=' * 50 + '\n')
    file.close()
  ```

* 打开方式

  * r：以只读方式打开文件，文件指针将会放在文件的开头，默认模式
  * rb：以二进制只读方式打开，指针放在开头
  * r+：以读写方式打开。指针放在开头
  * rb+：以二进制读写方式打开，指针放在开头
  * w：以写入方式打开，若文件已存在，则覆盖，若文件不存在，则创建新的文件
  * wb：以二进制写入方式打开，则覆盖，若文件不存在，则创建新的文件
  * w+：以读写方式打开，若文件已存在，则覆盖，若文件不存在，则创建新的文件
  * wb+：以二进制读写方式打开，若文件已存在，则覆盖，若文件不存在，则创建新的文件
  * a：以追加方式打开，若该文件已存在，文件指针将会放在文件结尾。即新的内容会被写入到已有内容之后，若文件不存在，则创建新的文件写入
  * ab：以二进制追加方式打开，若该文件已存在，文件指针将会放在文件结尾。即新的内容会被写入到已有内容之后，若文件不存在，则创建新的文件写入
  * a+：以读写方式打开一个文件，若该文件已存在，文件指针将会放在文件结尾。文件打开时会是追加模式，若文件不存在，则创建新的文件写入
  * ab+：以二进制追加方式代开，若该文件已存在，文件指针将会放在文件结尾。即新的内容会被写入到已有内容之后，若文件不存在，则创建新的文件写入

* 简化写法

  * with as语法，在with控制块结束时，文件会自动关闭，就不需要再调用close()方法了

    ```python
    with open('explore.txt','a',encoding='utf-8') as file:
        file.write('\n'.join([question,author,answer]))
        file.write('\n' + '=' *50 + '\n')
    ```

#### JSON文件存储

> JSON，全称JavaScript Object Notion，也就是JavaScript对象标记，它通过对象和数组的组合来表示数据，是一种轻量级的数据交换格式。

* 对象和数组

  * 对象：使用{}包裹起来的内容，数据结构为{key1:value1,key2:value2,…}的键值对结构。在面向对象的语言中，key为对象的属性，value为对应的值。键名可以使用整数和字符串表示。值得类型可以使任意类型。
  * 数组：使用[]包裹起来的内容，数据结构为["java","javascritpt","vb",…]的索引结构。在JavaScript中，数组是一种比较特殊的数据类型，它也可以像对象那样使用键值对，但还是索引用的多。同样，值可以是任意类型。

  ```json
  [
      {
          "name":"bob",
          "gender":"male",
          "birthday":"today"
      },
      {
          "name":"selina",
          "gender":"female",
          "birthday":"tomorrow"
      }
  ]
  ```

* 读取JSON：通过dumps()方法将JSON对象转为文本字符串

  ```python
  import json
  
  str = '''
  [
      {
          "name":"bob",
          "gender":"male",
          "birthday":"today"
      },
      {
          "name":"selina",
          "gender":"female",
          "birthday":"tomorrow"
      }
  ]
  '''
  print(type(str))
  data = json.loads(str)
  print(data)
  print(type(json))
  
  #添加索引获得字典元素，通过调用键名即可得到键值
  data[0]['name']
  data[0].get('name')
  data[0].get('age') # None
  data[0].get('age',25) # default value = 25
  
  # 从JSON文本读取内容
  with open('data.json','r') as file:
      str = file.read()
      data = json.loads(str)
      print(data)

  ```

  > JSON的数据需要用双引号来保卫，不能使用单引号，否则会出现JSONDecodeError错误

* 输出JSON：调用dumps()方法将JSON对象转换为字符串

  ```python
  import json
  
  data = [{
      'name':'王伟',
      'gender':'male',
      'birthday':'19920825'
  }]
  # 为了输出中文，还需要指定参数ensure_ascii=False,参数indent，代表缩进字符个数，另外还要规定文件输出的编码
  with open('data.json','w',encoding='utf-8') as file:
      file.write(json.dumps(data,indent=2,ensure_ascii=False))
  ```

#### CSV文件存储

> CSV，全称Comma-Separated Values，中文可以叫作逗号分隔值或字符分隔值，其文件以纯文本形式存储表格数据。该文件是一个字符序列，可以由任意数目的记录组成，记录间以某种换行符分隔。

* 写入

```python
import csv

# delimiter可以修改列与列之间的分隔符，writerrows可以同时写入多行，此时参数就需要为二位列表
with open('data.csv','w') as csvfile:
    writer = csv.writer(csvfile,delimiter=' ')
    writer.writerrow('id','name','age')
    writer.writerrows([['1001','mike',20],['1002','bob',22]])

# 写入字典
import csv

with open('data.csv','w',encoding='utf-8') as csvfile:
    fieldnames = ['id','name','age']
    writer = csv.DictWriter(csvfile,fieldnames=fieldnames)
    writer.writeheader()
    writer.writerow({'id':'1001','name':'mike','age':20})
    writer.writerows([{'id':'1002','name':'bob','age':21},{'id':'1003','name':'du','age':25}])

```

* 读取

  > 这里构造的Reader对象，通过遍历输出了每行的内容，每一个行都是一个列表形式。如果文件中包含中文的话，还需要指定文件编码。

  ```python
  with open('data.csv','r',encoding='utf-8') as csvfile:
      reader = csv.reader(csvfile)
      for row in reader:
          print(row)
  ```

  * 也可以使用pandas中的read_csv()方法将数据从CSV中读取出来

    ```python
    import pandas as pd

    df = pd.read_csv('data.csv')
    print(df)
    ```

### 5.2 关系型数据库存储

> 关系型数据库是基于关系模型的数据库，关系模型是通过二维表来保存的，所以它的存储方式就是行列组成的表，每一列就是一个字段，每一行就是一条记录。表可以看作某个实体的集合，而实体之间也存在联系，这就需要表与表之间的联系关系来体现，如主键外键的关联关系。多个表组成一个数据库，也就是关系型数据库。
>
> 关系型数据库有多种，如SQLite、MySQL、Oracle、SQL Server、DB2等。

#### MySQL存储

* 连接数据库

  ```python
  import pymysql
  
  # 通过PyMySQL的connect()方法声明一个MySQL连接duixiangdb
  db = pymysql.connect(host='localhost',user='root',password='',port=3306)
  # 连接成功后调用cursor()获取MySQL的操作游标
  cursor = db.cursor()
  # execute()方法执行sql语句
  cursor.execute('SELECT VERSION()')
  # 返回执行结果
  data = cursor.fetchone()
  print('Database version:',data)
  cursor.execute('CREATE DATABASE spiders DEFAULT CHARACTER SET UTF8')
  db.close()
  ```

* 创建表

  ```python
  import pymysql
  
  # 代码格式化 command + alt + L
  db = pymysql.connect(host='localhost', user='root', password='', port=3306, db='spiders')
  cursor = db.cursor()
  sql = 'CREATE TABLE IF NOT EXISTS students (id VARCHAR(255) NOT NULL ,name VARCHAR(255) NOT NULL,age INT NOT NULL,PRIMARY KEY (id))'
  cursor.execute(sql)
  db.close()
  ```

* 插入数据

  ```python
  import pymysql
  
  id = '20120001'
  user = 'bob'
  age = 20
  
  db = pymysql.connect(host='localhost', user='root', password='', port=3306, db='spiders')
  cursor = db.cursor()
  # 使用构造SQL语句：sql = 'INSERT INTO student(id,name,age) values(' + id + ', ' + name + ', ' + age + ')'
  # 使用格式化符%s实现，可以避免字符串拼接的麻烦，又可以避免引号冲突的问题
  sql = 'INSERT INTO students(id,name,age) values(%s,%s,%s)'
  try:
      cursor.execute(sql,(id,user,age))
      # 需要执行db对象的commit()方法才可实现数据插入，该方法可以将语句提交到数据库执行的方法
      # 对于数据插入、更新、删除操作，都需要调用该方法才能生效
      db.commit()
  except:
      # 如果执行失败，则调用rollback()执行数据回滚
      db.rollback()
  finally:
      db.close()
  ```

* 事务的4个属性（ACID）

  |         属性          | 解释                                                         |
  | :-------------------: | :----------------------------------------------------------- |
  |  原子性（atomicity）  | 事务是一个不可分割的工作单位，事务中包括的诸操作要么都做，要么都不做 |
  | 一致性（consistency） | 事务必须使数据库从一个一致性状态变到另一个一致性状态。一致性与原子性是密切相关的 |
  |  隔离性（isolation）  | 一个事务的执行不能被其他事务干扰，即一个事务内部的操作及使用的数据对并发的其他事务是隔离的，并发执行的各个事务之间不能相互干扰 |
  | 持久性（durability）  | 持久性也称永久性（permanence），指一个事务一旦提交，它对数据库的改变就应该是永久的。接下来的其他操作或故障不应该对其有任何影响 |

  ```python
  import pymysql
  
  db = pymysql.connect(host='localhost', user='root', password='', port=3306, db='spiders')
  cursor = db.cursor()
  # 优化
  data = {
      'id':'20120002',
      'name':'bob',
      'age':20
  }
  table = 'students'
  keys = ', '.join(data.keys())
  values = ', '.join(['%s'] * len(data))
  sql = 'INSERT INTO {table}({keys}) VALUES ({values})'.format(table=table,keys=keys,values=values)
  try:
      if cursor.execute(sql,tuple(data.values())):
          print('successful')
          db.commit()
  except:
      print('failed')
      db.rollback()
  finally:
      db.close()
  ```

* 更新数据

  ```python
  import pymysql
  
  db = pymysql.connect(host='localhost', user='root', password='', port=3306, db='spiders')
  cursor = db.cursor()
  
  data = {
      'id':'20120001',
      'name':'bob',
      'age':25
  }
  
  table = 'students'
  keys = ', '.join(data.keys())
  values = ', '.join(['%s'] * len(data))
  
  # ON DUPLICATE KEY UPDATE 如果主键存在，就执行更新操作
  sql = 'INSERT INTO {table}({keys}) VALUES({values}) ON DUPLICATE KEY UPDATE'.format(table=table,keys=keys,values=values)
  update = ','.join([" {key} = %s".format(key = key) for key in data])
  sql += update
  # 若执行更新操作，则sql语句就是
  # INSERT INTO students(id, name, age) VALUES(%s, %s, %s) ON DUPLICATE KEY UPDATE id = %s, name = %s, age = %s
  # 这里就变成了6个%s，所以在后面的excute()方法的第二个参数元组就需要乘以2编程原来的2倍
  try:
      print(sql)
      if cursor.execute(sql,tuple(data.values()) * 2):
          print('successful')
          db.commit()
  except:
      print('failed')
      db.rollback()
  finally:
      db.close()
  ```

* 删除数据

  ```python
  table = 'students'
  condition = 'age > 20'
  
  # 因为删除条件有多种多样，所以不再继续构造复杂的判断性。这里之间将条件当做字符串来传递，以实现删除操作
  sql = 'DELETE FROM {table} WHERE {condition}'.format(table=table,condition=condition)
  try:
      cursor.excute(sql)
      db.commit()
  except:
      db.rollback()
  finally:
      db.close
  ```

* 查询数据

  ```python
  import pymysql
  
  db = pymysql.connect(host='localhost', user='root', password='', port=3306, db='spiders')
  cursor = db.cursor()
  
  sql = 'SELECT * FROM students WHERE age >= 19'
  try:
      cursor.execute(sql)
      print('Count:',cursor.rowcount)
      # 内部有一个偏移指针用来指向查询结果，最开始偏移指针指向第一条数据，取一次以后，指针指向下一条数	   据，这样再取得话，就会取到下一条数据
      # one = cursor.fetchone()
      # print('One:',one)
      result = cursor.fetchall()
      print('Result:',result)
      print('Result Type:',type(result))
      for row in result:
          print(row)
  except:
      print("Error")
  finally:
      db.close()

  # 结果：
  Count: 2
  One: ('20120001', 'bob', 25)
  Result: (('20120002', 'bob', 20),)
  Result Type: <class 'tuple'>
  ('20120002', 'bob', 20)
  ```

### 非关系型存储

> NoSQL，全称Not Only SQL，意为不仅仅是SQL，泛指非关系型数据库。NoSQL是基于键值对的，而且不需要经过SQL层的解析，数据之间没有耦合性，性能非常高。

* 分类
  * 键值存储数据库：Redis、Voldemort和Oracle BDB等
  * 列存储数据库：Cassandra、HBase和Riak等
  * 文档型数据库：CouchDB和MongoDB等
  * 图形数据库：Neo4J、InfoGrid和Infinite Graph等

#### MongoDB存储

* 连接MongoDB，连接数据库并插入、查询数据

  ```python
  import pymongo
  from pymongo import MongoClient
  
  # 连接数据库
  client = MongoClient('mongodb://localhost:27017/')
  # client = pymongo.MongoClient(host='localhost',prot=27017)
  
  # 指定数据库，两种方式等价
  # db = client.test
  db = client['test']
  
  # 指定集合
  # collection = db.student
  collection = db['student']
  
  # 插入数据
  student = {
      'id':'20170101',
      'name':'jordan',
      'age':20,
      'gender':'male'
  }
  
  student1 = {
      'id':'20170102',
      'name':'mike',
      'age':20,
      'gender':'male'
  }
  
  student2 = {
      'id':'20170103',
      'name':'du',
      'age':20,
      'gender':'male'
  }
  
  # 插入一条数据并返回_id值
  # result = collection.insert_one(student)
  # print(result.inserted_id)
  
  # 插入多条数据
  # result = collection.insert_many([student1,student2])
  # print(result.inserted_ids)
  
  # 查询数据 利用find_one()或find()方法进行查询
  result = collection.find_one({'name':'mike'})
  print(type(result))
  print(result)
  
  results = collection.find({'age':20})
  print(results)
  for r in results:
      print(r)
  
  # 查询年龄大于20的数据
  results = collection.find({'age':{'$gt':19}})
  print(results)
  for r in results:
      print(r)
  ```

* 查询符号表

  ![img](https://ws4.sinaimg.cn/large/006tNc79ly1fteyfoplygj30ml06ngmq.jpg)

  ![img](https://ws2.sinaimg.cn/large/006tNc79ly1fteyjn2frlj30ml06eq4b.jpg)

* 计数

  ```python
  count = collection.find().count()
  print(count)
  
  count = collection.find({'age':20}).count()
  print(count)
  ```

* 排序

  ```python
  # 升序：pymongo.ASCENDING 降序：pymongo.DESCENDING
  results = collection.find.sort('name',pymongo.ASCENDING)
  print([result['name'] for result in results])
  ```

* 偏移

  ```python
  # 忽略前两个元素
  results = collection.find().sort('name',pymongo.ASCENDING).skip(2)
  print([result['name'] for result in results])
  
  # 忽略前两个元素并只取2个元素结果
  results = collection.find().sort('name',pymongo.ASCENDING).skip(2).limit(2)
  print([result['name'] for result in results])
  ```

* 更新

  ```python
  # 更新数据
  condition = {'name':'du'}
  student = collection.find_one(condition)
  student['age'] = 25
  # 建议使用update_one或update_many
  # result = collection.update(condition,student)
  # 也可以使用$set操作符对数据进行更新，这样可以只更新student字典内存在的字段，如果原先还有其他字段，则不会更新也不会删除。
  # result = collection.update(condition,{'$set':student})
  print(result)
  
  condition = {'name':'mike'}
  student = collection.find_one(condition)
  student['age'] = 26
  result = collection.update_one(condition,{'$set':student})
  print(result)
  print(result.matched_count,result.modified_count)
  
  condition = {'age':{'$gt':20}}
  # 第一条符合条件的年龄+1
  # result = collection.update_one(condition,{'$inc':{'age':1}})
  result = collection.update_many(condition,{'$inc':{'age':1}})
  print(result)
  print(result.matched_count,result.modified_count)
  ```

* 删除

  ```python
  # 删除
  result = collection.delete_one({'name':'mike'})
  print(result)
  print(result.deleted_count)
  result = collection.delete_many({'age':20})
  print(result)
  print(result.deleted_count)
  ```

* 其他方法

  * find_one_and_delete()、finde_one_and_replace()和find_one_and_update()等
  * create_index()、create_indexes()和drop_index()等
  * 操作指南：[https://docs.mongodb.com/guides/](https://docs.mongodb.com/guides/)
  * PyMongo官方文档：[http://api.mongodb.com/python/current/api/pymongo/collection.html](http://api.mongodb.com/python/current/api/pymongo/collection.html)

#### Redis存储

> Redis是一个基于内存的高效的键值型非关系型数据库，存取效率极高，而且支持多种存储数据结构，使用简单。

* 启动redis服务端

  ```bash
  # 启动redis数据库服务端
  redis-server
  # 使用密码启动redis客户端
  redis-cli -a 1234
  ```

* Redis和StrictRedis

  redis-py库提供两个类Redis和StrictRedis来实现Redis的命令操作（官方推荐使用StrictRedis）

* 连接Redis

  ```python
  from redis import StrictRedis,ConnectionPool
  
  # 使用ConnectionPool连接
  pool = ConnectionPool(host='localhost',port=6379,db=0,password='1234')
  
  ''''
  # ConnectionPool还支持通过URL来构建
  # Redis TCP连接
  redis://[:passwrod]@host:port/db
  
  # Redis TCP+SSL连接
  rediss://[:passwrod]@host:port/db
  
  # Reids UNIX socket连接
  unix://[:password]@path/to/socket.sock?db=db
  
  url = 'redis://:1234@localhost:6379/0'
  pool = ConnectionPoo;.from_url(url)
  redis = StrictRedis(connection_pool=pool)
  '''
  # redis = StrictRedis(host='localhost',port=6379,db=0,password='1234')
  
  redis = StrictRedis(connection_pool=pool)
  redis.set('name','duzhida')
  print(redis.get('name'))
  ```

## 六、Ajax数据爬取

### 6.1 什么是Ajax

### 什么是Ajax

> Ajax全称为Asynchronous JavaScript and XML，即异步的JavaScript和XML。它不是一门编程语言，而是利用JavaScript在保证页面不被刷新，页面链接不改变的情况下与服务器交换数据并更新部分网页的的技术。

#### 基本原理

* 实例引入：很多网页都有下滑查看更多的选项，下滑页面会出现加载动画，一段时间过后才会出现新的内容，这个过程就是Ajax加载的过程。

* 发送Ajax请求到网页更新的过程分为以下3步：

  1. 发送请求
  2. 解析内容
  3. 渲染网页

* 发送请求

  ```javascript
  // 这个JavaScript对Ajax最底层的实现，实际上就是新建了XMLHttpReequest对象，然后调用onreadystatechange属性设置了监听，然后调用open()和send()方法向某个链接(服务器)发送请求
  var xmlhttp;
  if(window.XMLHttpRequest){
      //code for IE7+,Firfox,Chrome,Opera,Safari
      xmlhttp = new XMLHttpRequest();
  }else{
      //code for IE6,IE5
      xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
  }
  
  xmlhttp.onreadystatechange=function(){
      if(xmlhttp.readyState == 4 && xmlhttp.status == 200){
          document.getElementById("myDiv").innerHTML = xmlhttp.responseText;
      }
  }
  xmlhttp.open("POST","/ajax/",true);
  xmlhttp.send()
  ```

* 解析内容

  得到相应之后，onreadystatechange属性对应的方法就会触发，此时利用xmlhttp的responseText属性便可取到响应内容。返回的内容可能是HTML，可能是JSON，接下来只需要在方法中用JavaScript进一步处理即可。

* 渲染网页

  JavaScript有改变网页内容的能力，解析完响应内容之后，就可以调用JavaScript来针对解析完的内容对网页进行下一步处理。比如，通过document。getElementById().innerHTML就可以对元素内的源代码进行更改。这样网页显示的内容就改变了，这样的操作也被称为DOM操作。

### 6.2 Ajax分析方法

1. 查看请求

   ![img](/var/folders/g_/cckjvp_d1b39h60g3s9grbp00000gn/T/abnerworks.Typora/image.tiff)

   ![img](/var/folders/g_/cckjvp_d1b39h60g3s9grbp00000gn/T/abnerworks.Typora/image-20180810214920108.tiff)

   XHR即是Ajax特殊的请求类型。

2. 过滤请求

   ![img](https://ws4.sinaimg.cn/large/0069RVTdgy1fu4y2uiikhj31kw0v5174.jpg)

### 6.3 Ajax结果提取

* 分析请求

### 6.4 分析Ajax爬取今日头条街拍美图

* 抓取分析

  * 目标：[https://www.toutiao.com/search/?keyword=%E8%A1%97%E6%8B%8D](https://www.toutiao.com/search/?keyword=%E8%A1%97%E6%8B%8D)

* 实战演练

  ```python
  import json
  import os
  from hashlib import md5
  import re
  import time
  from urllib.parse import urlencode
  import requests
  from bs4 import BeautifulSoup
  from requests import RequestException
  from spider_toutiao.config import *
  from multiprocessing import Pool

  '''
  流程框架：
  1. 抓取索引页内容
    利用requests请求目标站点，得到索引网页HTML代码，返回结果
  2. 抓取详情页内容
    解析返回结果，得到详情页的链接，并进一步抓取详情页的信息
  3. 下载图片与保存数据库
    将图片下载到本地，并把页面信息及图片URL保存至MongoDB
  4. 开启循环及多线程
    对多页内容遍历，开启多线程提高抓取速度
  '''

  # 获取主页源代码
  def get_page_index(offset,keyword):
      data = {
          'offset': offset,
          'format': 'json',
          'keyword': keyword,
          'autoload': 'true',
          'count': '20',
          'cur_tab': 3
      }
      # 构造目的地址的url链接
      url = 'https://www.toutiao.com/search_content/?' + urlencode(data)
      try:
          response = requests.get(url)
          if response.status_code == 200:
              return response.text
          return None
      except RequestException:
          print('请求索引页错误')
          return None

  
  # 解析获取到的主页源码
  def parse_page_index(html):
      data = json.loads(html)
      if data and 'data' in data.keys():
          for item in data.get('data'):
              yield item.get('article_url')

  
  # 获取详情页的页面源码
  def get_page_detail(url):
      try:
          headers = {
              'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/69.0.3497.100 Safari/537.36'
          }
          response = requests.get(url,headers=headers)
          if response.status_code == 200:
              return response.text
          return None
      except RequestException:
          print('请求详情页页错误', url)
          return None

  
  # 解析详情页的代码，获取相关的title，url和images的url链接
  def parse_page_detail(html,url):
      # 使用BeautifulSoup解析获取的详情页源码，从中提取出包含图片的标题，url和图片url
      soup = BeautifulSoup(html,'lxml')
      title = soup.select("title")[0].get_text()
      images_pattern = re.compile('gallery: JSON.parse\((.*?)\),',re.S)
      results = re.search(images_pattern,html)
      if results:
          data = json.loads(json.loads(results.group(1)))
          if data and 'sub_images' in data.keys():
              sub_images = data.get('sub_images')
              images = [item.get('url') for item in sub_images]
              for image in images:
                  download_image(image,title)
              return {
                  'title': title,
                  'url': url,
                  'images': images
              }


  # 下载图片
  def download_image(url, title):
      print("正在下载：" + title)
      try:
          response = requests.get(url)
          if response.status_code == 200:
              save_image(response.content,title)
      except RequestException:
          print('请求图片出错', url)
          return None

  
  # 保存图片到本地
  def save_image(content, title):
      if not os.path.exists(title):
          os.mkdir(title)
      file_path = '{0}/{1}.{2}'.format(title,md5(content).hexdigest(),'jpg')
      if not os.path.exists(file_path):
          with open(file_path,'wb') as f:
              f.write(content)
              f.close()

  
  # main函数
  def main():
      for i in range(OFFSET):
          html = get_page_index(20 * i,KEYWORD + '图集')
          for url in parse_page_index(html):
              html = get_page_detail(url)
              time.sleep(1)
              if html:
                  parse_page_detail(html,url)

  
  # 程序入口
  if __name__ == '__main__':
      # 以下代码开启多进程，但多进程可能会导致封IP，因此暂时不适用多线程
      # groups = [x * 20 for x in range(GROUP_START,GROUP_END + 1)]
      # pool = Pool()
      # pool.map(main, groups)
      main()
  ```

### Ajax分析方法

1. 查看请求
2. 过滤请求

## 七、动态渲染页面爬取

### 7.1 Selenium的使用

> Selenium是一个自动化测试工具，利用它可以驱动浏览器执行特定的动作，如点击、下拉等操作，同时还可以获取浏览器当前呈现的页面的源代码，做到可见既可爬。

* 安装selenium

  `pip install selenium`

  * 安装chromedriver

    * [下载地址](http://chromedriver.chromium.org/downloads)

    * 解压并移动到python安装目录下`sudo mv chromedriver /usr/bin`

    * 配置ChromeDriver到$PATH

      ```bash
      export PATH="$PATH:/usr/local/chromedriver"
      source ~/.profile
      ```

    * 输出`Only local connections are allowed`则配置完成

* 基本使用

  ```python
  from selenium import webdriver
  from selenium.webdriver.common.by import By
  from selenium.webdriver.common.keys import Keys
  from selenium.webdriver.support import expected_conditions as EC
  from selenium.webdriver.support.wait import WebDriverWait
  
  brower = webdriver.Chrome()
  
  try:
      brower.get('https://www.baidu.com')
      input = brower.find_element_by_id('kw')
      input.send_keys('Python')
      input.send_keys(Keys.ENTER)
      wait = WebDriverWait(brower,1000)
      wait.until(EC.presence_of_element_located((By.ID,'content_left')))
      print(brower.current_url)
      # print(brower.get_cookies())
      # print(brower.page_source)
  finally:
      brower.close()
  ```

  * 声明浏览器支持对象

    ```python
    from selenium import webdriver

    browser = webdriver.Chrome()
    browser = webdriver.Firefox()
    browser = webdriver.Edge()
    browser = webdriver.PhantomJS()
    browser = webdriver.Safari()
    ```

  * 访问页面

    ```python
    from selenium import webdriver

    browser = webdriver.Chrome()
    browser.get('https://www.taobao.com')
    print(browser.page_source)
    browser.close()
    ```

  * 查找节点

    * 单个节点，可以根据name、id获取，还可以根据XPath、CSS选择器等获取的方式

      ```python
      from selenium import webdriver

      browser = webdriver.Chrome()
      browser.get('https://www.taobao.com')
      input_first = browser.find_element_by_id('q')
      input_second = browser.find_element_by_css_selector('#q')
      input_third = browser.find_element_by_xpath('//*[@id="q"]')
      print(input_first,input_second,input_third)
      browser.close()

      # 所有获取单个节点的方法
      browser.find_element_by_id()
      browser.find_element_by_name()
      browser.find_element_by_xpath()
      browser.find_element_by_link_text()
      browser.find_element_by_tag_name()
      browser.find_element_by_class_name()
      browser.find_element_by_css_selector()

      # 通用方法
      browser.find_element(By.ID,id)
      ```

    * 多个节点

      ```python
      from selenium import webdriver

      browser = webdriver.Chrome()
      browser.get('https://www.taobao.com')
      lis = browser.find_elements_by_css_selector('.service-bd li')
      print(lis)
      browser.close()

      # 所有获取多个节点的方法
      browser.find_elements_by_id()
      browser.find_elements_by_name()
      browser.find_elements_by_xpath()
      browser.find_elements_by_link_text()
      browser.find_elements_by_partial_link_text()
      browser.find_elements_by_tag_name()
      browser.find_elements_by_class_name()
      browser.find_elements_by_css_selector()

      # 通用方法
      browser.find_elements(By.ID,id)
      ```

  * 节点交互

    * 常见用法有：输入文字send_keys()方法，清空文字clear()方法，点击按钮click()方法

    ```python
    from selenium import webdriver
    import time

    browser = webdriver.Chrome()
    browser.get('https://www.taobao.com')
    input = browser.find_element_by_id('q')
    input.send_keys('iPhone')
    time.sleep(5)
    input.clear()
    input.send_keys('ipad')
    button = browser.find_element_by_class_name('btn-search')
    button.click()
    ```

    > [官方文档](http://selenium-python.readthedocs.io/api.html#module-selenium.webdriver.remote.webelement)

  * 动作链

    ```python
    from selenium import webdriver
    from selenium.webdriver import ActionChains

    browser = webdriver.Chrome()
    url = 'http://www.runoob.com/try/try.php?filename=jqueryui-example-droppable'
    browser.get(url)
    browser.switch_to.frame('iframeResult')
    source = browser.find_element_by_css_selector('#draggable')
    target = browser.find_element_by_css_selector('#droppable')
    actions = ActionChains(browser)
    actions.drag_and_drop(source,target)
    actions.perform()
    ```

  * 执行JavaScript

    ```python
    from selenium import webdriver

    browser = webdriver.Chrome()
    browser.get('https://www.zhihu.com/explore')
    browser.execute_script('window.scrollTo(0,document.body.scrollHeight)')
    browser.execute_script('alert("To Bottom")')
    ```

  * 获取节点信息

    * 获取属性

      ```python
      from selenium import webdriver
      from selenium.webdriver import ActionChains

      browser = webdriver.Chrome()
      url = 'https://www.zhihu.com/explore'
      browser.get(url)
      logo = browser.find_element_by_id('zh-top-link-logo')
      print(logo)
      print(logo.get_attribute('class'))
      ```

    * 获取文本值

      ```python
      from selenium import webdriver

      browser = webdriver.Chrome()
      url = 'https://www.zhihu.com/explore'
      browser.get(url)
      input = browser.find_element_by_class_name('js-signin-noauth')
      print(input.text)
      ```

    * 获取id、位置、标签名和大小

      ```python
      from selenium import webdriver

      browser = webdriver.Chrome()
      url = 'https://www.zhihu.com/explore'
      browser.get(url)
      input = browser.find_element_by_class_name('zu-top-add-question')
      print(input.id)
      print(input.location)
      print(input.tag_name)
      print(input.size)
      ```

  * 切换Frame

    网页中有一种节点叫作iframe，它的结构和外部网页的结构完全一致。Selenium打开网页后，它默认实在父级Frame里面操作，如果页面中还有子Frame，它是不能获取到子Frame里面的节点的，需要使用switch_to.frame()方法来切换Frame。

    ```python
    import time
    from selenium import webdriver
    from selenium.common.exceptions import NoSuchElementException

    browser = webdriver.Chrome()
    url = 'http://www.runoob.com/try/try.php?filename=jqueryui-api-droppable'
    browser.get(url)
    browser.switch_to.frame('iframeResult')
    try:
        logo = browser.find_element_by_class_name('logo')
    except NoSuchElementException:
        print('no logo')
    browser.switch_to.parent_frame()
    logo = browser.find_element_by_class_name('logo')
    print(logo)
    print(logo.text)
    ```

  * 延时等待

    在Selenium中，get()方法会在网页框架加载结束后结束执行，但可能并不是浏览器完全加载完成的页面，所以需要延时等待一定时间，确保节点已经加载出来。

    * 隐式等待

      使用隐式等待执行测试的时候，如果Selenium没有在DOM中找到节点，将继续等待，超出设定时间则抛出找不到节点的异常，默认时间为0。

      ```python
      from selenium import webdriver

      option = webdriver.ChromeOptions()
      option.add_argument('-headless')
      browser = webdriver.Chrome(options=option)
      browser.implicitly_wait(10)
      browser.get('https://www.zhihu.com/explore')
      input = browser.find_element_by_class_name('zu-top-add-question')
      print(input)
      ```

    * 显式等待

      显式等待指定要查找的节点，然后指定一个最长等待时间。如果在规定时间内加载出该节点，就返回查找的节点；如果未加载出该节点，则抛出异常。

      ```python
      from selenium import webdriver
      from selenium.webdriver.common.by import By
      from selenium.webdriver.support.ui import WebDriverWait
      from selenium.webdriver.support import expected_conditions as EC

      option = webdriver.ChromeOptions()
      option.add_argument('-headless')
      browser = webdriver.Chrome(options=option)
      # browser = webdriver.Chrome()
      browser.get('https://www.taobao.com/')
      wait = WebDriverWait(browser,10)
      # presence_of_element_located的参数是节点的定位元祖，也就是ID为q的节点搜索框
      input = wait.until(EC.presence_of_element_located((By.ID,'q')))
      button = wait.until(EC.element_to_be_clickable((By.CSS_SELECTOR,'.btn-search')))
      print(input,button)
      ```

      * 其他等待条件

        | 等待条件                               | 含义                                            |
        | -------------------------------------- | ----------------------------------------------- |
        | title_is                               | 标题是某内容                                    |
        | title_contains                         | 标题包含某内容                                  |
        | presence_of_element_located            | 节点加载出来，传入定位元祖                      |
        | visibility_of+element_located          | 节点可见，传入定位元祖                          |
        | visibility_of                          | 可见，传入节点对象                              |
        | presence_of_all_elements_located       | 所有节点加载出来                                |
        | text_to_be_present_in_element          | 某个节点文本包含某文字                          |
        | text_to_bo_present_in_element_value    | 某个节点值包含某文字                            |
        | frame_to_bo_available_and_switch_to_it | 加载并切换                                      |
        | invisibility_of_element_located        | 节点不可见                                      |
        | element_to_be_clickable                | 节点可点击                                      |
        | staleness_of                           | 判断一个节点是否仍在DOM，可判断页面是否已经刷新 |
        | element_to_be_selected                 | 节点可选择，传入节点对象                        |
        | element_located_to_be_selected         | 节点可选择，传入定位元祖                        |
        | element_selection_state_to_be          | 传入节点对象及状态，相等为True，否则False       |
        | element_located_selection_state_to_be  | 传入定位元祖及状态，相等为True，否则False       |
        | alert_is_present                       | 是否出现警告                                    |

        > [更多参考官方文档](http://selenium-python.readthedocs.io/api.html#module-selenium.webdriver.support.expected_conditions)

  * 前进和后退

    ```python
    import time
    from selenium import webdriver

    browser = webdriver.Chrome()
    browser.get('https://www.taobao.com')
    browser.get('https://www.taobao.com')
    browser.get('https://www.baidu.com')
    browser.back()
    time.sleep(1)
    browser.forward()
    browser.close()
    ```

  * Cookies

    ```python
    from selenium import webdriver

    option = webdriver.ChromeOptions()
    option.add_argument('-headless')
    browser = webdriver.Chrome(options=option)
    browser.get('https://www.zhihu.com/explore')
    print(browser.get_cookies())
    browser.add_cookie({'name':'name','domain':'www.zhihu.com','value':'germey'})
    print('-' * 50)
    print(browser.get_cookies())
    browser.delete_all_cookies()
    print(browser.get_cookies())
    ```

  * 选项卡管理

    ```python
    import time
    from selenium import webdriver

    browser = webdriver.Chrome()
    browser.get('https://www.baidu.com')
    browser.execute_script('window.open()')
    print(browser.window_handles)
    browser.switch_to_window(browser.window_handles[1])
    browser.get('https://www.taobao.com')
    time.sleep(1)
    browser.switch_to_window(browser.window_handles[0])
    browser.get('https://www.python.org')
    ```

  * 异常处理

    ```python
    from selenium import webdriver
    from selenium.common.exceptions import TimeoutException,NoSuchElementException

    browser = webdriver.Chrome()
    try:
        browser.get('https://www.baidu.com')
    except TimeoutException:
        print('time out')
    try:
        browser.find_element_by_id('hello')
    except NoSuchElementException:
        print('no element')
    finally:
        browser.close()

    ```

### 7.2 Splash的使用

* 功能
  * 异步方式处理多个网页渲染过程
  * 获取渲染后的页面的源代码或截图
  * 通过关闭图片渲染或使用adblock规则来加快页面渲染速度
  * 可执行特定的JavaScript脚本
  * 可通过Lua脚本来控制页面渲染速度
  * 获取渲染的详细过程病通过HAR格式呈现
* 安装
  * 安装docker`brew cask install docker`
  * 现在安装spalsh`docker pull scrapinghub/splash`
  * 运行spalsh`docker run -p 8050:8050 -p 5023:5023 scrapinghub/splash`
  * 使用浏览器访问`http://localhost:8050`
* 

### 7.3 Splash负载均衡配置

### 7.4 使用Selenium爬取淘宝商品

> 使用Selenium模拟浏览器操作，抓取淘宝的商品信息，并将结果保存到MongoDB

目标地址：[https://s.taobao.com/search?q=美食](https://s.taobao.com/search?q=美食)

![meishi](https://ws2.sinaimg.cn/large/006tNbRwgy1fvm5on4s0lj311h0opqv5.jpg)

步骤：
1. 搜索关键词

  利用Selenium驱动浏览器搜索关键词，得到查询后的商品列表

2. 分析页码并翻页

  得到商品页码数，模拟翻页，得到后续页面的商品列表

3. 分析提取商品内容

  利用PyQuery分析源码，解析得到商品列表

4. 存储至mongoDB

  将商品列表存储至数据库MongoDB

代码
```python
from selenium import webdriver
from selenium.common.exceptions import TimeoutException
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import re
from pyquery import PyQuery as pq
from config import *
import pymongo

MONGO_URL = 'localhost'
MONGO_DB = 'taobao'
MONGO_TABLE = 'product'
client = pymongo.MongoClient(MONGO_URL)
db = client[MONGO_DB]
option = webdriver.ChromeOptions()
option.add_argument('-headless')
browser = webdriver.Chrome(options=option)
# browser = webdriver.Chrome()
wait = WebDriverWait(browser, 10)


def search():
    try:
        browser.get('https://www.taobao.com')
        input = wait.until(
            EC.presence_of_element_located((By.CSS_SELECTOR, "#q"))
        )
        submit = wait.until(
            EC.element_to_be_clickable((By.CSS_SELECTOR, "#J_TSearchForm > div.search-button > button"))
        )
        input.send_keys('美食')
        submit.click()
        total = wait.until(EC.presence_of_element_located((By.CSS_SELECTOR,'#mainsrp-pager > div > div > div > div.total')))
        get_products()
        return total.text
    except TimeoutException:
        return search()


def next_page(page_number):
    try:
        input = wait.until(
            EC.presence_of_element_located((By.CSS_SELECTOR, "#mainsrp-pager > div > div > div > div.form > input"))
        )
        submit = wait.until(
            EC.element_to_be_clickable((By.CSS_SELECTOR, "#mainsrp-pager > div > div > div > div.form > span.btn.J_Submit"))
        )
        input.clear()
        input.send_keys(page_number)
        submit.click()
        wait.until(EC.text_to_be_present_in_element((By.CSS_SELECTOR,'#mainsrp-pager > div > div > div > ul > li.item.active > span'),str(page_number)))
        get_products()
    except TimeoutException:
        next_page(page_number)


def get_products():
    wait.until(EC.presence_of_element_located((By.CSS_SELECTOR,'#mainsrp-itemlist .items .item')))
    html = browser.page_source
    doc = pq(html)
    items = doc('#mainsrp-itemlist .items .item').items()
    for item in items:
        product = {
            'title': item.find('.title').text(),
            'price': item.find('.price').text(),
            'location': item.find('.location').text(),
            'image': item.find('.pic .img').attr('data-src'),
            'deal': item.find('.deal-cnt').text()[:-3],
            'shop': item.find('.shop').text(),
        }
        # print(product)
        save_to_mongo(product)


def save_to_mongo(result):
    try:
        if db[MONGO_TABLE].insert(result):
            print('存储成功',result)
    except Exception:
        print('存储失败',result)


def main():
    total = search()
    total = int(re.compile(('(\d+)')).search(total).group(1))
    for i in range(2,total + 1):
        next_page(i)
    browser.close()


if __name__ == '__main__':
    main()
```

## 八、验证码识别

### 8.1 图形验证码的识别

## 九、代理的使用

## 十、模拟登陆

## 十一、APP的爬取

## 十二、 pyspider框架的使用

* 相关链接
  * GItHub地址：[https://github.com/binux/pyspider](https://github.com/binux/pyspider)
  * 官方文档：[http://docs.pyspider.org/en/latest/](http://docs.pyspider.org/en/latest/)
* 基本功能
  * 提供方便易用的WebUI系统，可视化编写和调试爬虫
  * 提供爬取进度监控、爬取结果查看、爬虫项目管理等功能
  * 支持多种后端数据库，如MySQL、MongoDB、Redis、SQLite、Elasticsearch、PostgreSQL
  * 支持多种消息队列，如RabbitMQ、Beanstalk、Redis、Kombu
  * 提供优先级控制、失败重试、定时抓取等功能
  * 对接了PhantomJS，可以爬取JavaScript渲染的页面
  * 支持单机和分布式部署，支持Docker部署
* 与Scrapy比较
* 架构

![pyspider](https://ws4.sinaimg.cn/large/006tNc79gy1fvqu6zgoenj307f07cq4y.jpg)

1. Scheduler 发起任务调度
2. Fetcher 负责抓取网页内容
3. Processer 负责解析网页内容
4. 将新生成的Request发给Scheduler进行调度
5. 将生成的提取结果输出保存

具体过程：

* 每个ppyspder的项目对应一个Python脚本，脚本中定义了一个Handler类，它有一个on_start()方法。爬取首先调用on_start()方法生成最初的抓取任务，然后发送给Scheduler进行调度。

* Scheduler将抓取任务分发给Fetcher进行抓取，Fetcher执行并得到响应，随后将响应发送给Processer。

* Processer处理响应并提取出新的URL生成新的抓取任务，然后通过消息队列的方式通知Schduler当前抓取任务执行情况，并将新生成的抓取任务发送给Scheduler。若生成了新的提取结果，则将其发送给结果队列等待Result Worker处理。

* Scheduler接收到新的任务，然后查询数据库，判断其如果是新的抓取任务或者是需要重试的任务就继续进行调度，然后将其发送给Fetcher进行抓取。

* 不断重复以上工作，指导所有的任务都执行完毕，抓取结束。

* 抓取结束后，程序会调用on_finished()方法，这里可以自定义后处理过程。

* 基本使用
  * 目标：爬去去哪儿网的旅游攻略，链接为[http://travel.qunar.com/travelbook/list.htm](http://travel.qunar.com/travelbook/list.htm)



## 十三、Scrapy框架的使用

## 十四、分布式爬虫

## 十五、分布式爬虫的部署

> 待更新2018.09.11