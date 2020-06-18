<h1 align="center">第 1 章 HTTP 概述</h1>

Web 浏览器、服务器和相关的 Web 应用程序都是通过 HTTP 相互通信的。HTTP 是现代全球因特网中使用的公共语言。

---

## HTTP 

HTTP 使用的是可靠的传输协议，即使数据来自地球另一端，也能确保数据不会在传输过程中损坏或混乱。这样用户不用担心其完整性，应用程序开发人员也无需担心 HTTP 通信在传输中被破坏、复制或畸变了，开发人员可以专注于应用程序特有细节的编写，而不用考虑因特网中的一些缺陷和问题。

## Web 客户端和服务器

Web 内容被存储在 Web 服务器上，Web 服务器使用的是 HTTP 协议，因此常被称为 HTTP 服务器。

Web 客户端和服务器
![Web 客户端和服务器](https://user-images.githubusercontent.com/37435717/84215949-99606a00-aafa-11ea-8017-9fcfb46cbfda.png)

平常最常见的 HTTP 客户端就是 Web 浏览器。浏览一个页面时，浏览器向服务器发送一条 HTTP 请求，服务器如果找到期望的对象，就将对象、对象类型、对象长度和其他信息放在 HTTP 响应中发送给客户端。

## 资源（resource）

Web 服务器是 Web 资源（Web resource）的**宿主**。Web 资源是 Web 内容的源头。

**Web 资源**可以是 Web 服务器文件系统中的静态文件，也可以是根据需要生成内容的软件程序，动态内容资源可以实时显示摄像头内容、交易股票、搜索数据、购买商品等等，可以根据身份、请求信息、时段等不同来产生不同内容。

所有能够提供 Web 内容的东西都是 Web 资源
![所有能够提供 Web 内容的东西都是 Web 资源](https://user-images.githubusercontent.com/37435717/84216539-733bc980-aafc-11ea-9491-875851a91838.png)

只要是内容来源就是资源，扫描图书馆书架的 Web 网关是资源，因特网搜索引擎也是资源

### 多媒体类型

**MIME 类型**（MIME type）（MIME：Multipurpose Internet Mail Extension，多用途因特网邮件扩展）发源于电子邮件系统，又被 HTTP 采纳以标记因特网上各种不同数据类型的多媒体内容。

> [maɪm]

Web 服务器会为所有 HTTP 对象数据附加一个 MIME 类型。Web 浏览器取回对象时会去查看相关的 MIME 类型，看是否知道应该如何处理这个对象。

![MIME 类型的返回](https://user-images.githubusercontent.com/37435717/84217132-ea259200-aafd-11ea-8dd7-a97b4ecdf963.png)

MIME 类型是一种文本标记，由主类型和子类型构成，中间由斜杠分隔。如 HTML 文档为 `text/html`；ASCII 文档为 `text/plain`；GIF 图片为 `image/gif`。[附录 D](./appendix-d.md) 提供了完整的 MIME 类型。

### URI

统一资源标识符 Uniform Resource Identifier，在世界范围内唯一标识并定位信息资源。URI 有 URL 和 URN 两种形式。

### URL

统一资源定位符是 URI 最常见的形式，描述了一台特定服务器上某资源的特定位置，可以明确说明如何从一个精确、固定的位置获取资源

大部分 URL 遵循一种标准格式：
- 方案（scheme），说明访问资源使用的协议类型，如 http:// 代表 HTTP 协议
- 服务器的因特网地址，如 www.github.com
- 具体哪个资源，如 /9527q/HTTP-The-Definitive-Guide

### URN

统一资源名是作为特定内容的唯一名称使用的，与资源当前所在地无关，它的应用需要一个支撑架构来解析资源的位置。使用这种方案就可以将资源随处搬运。通过 URN 还可以用同一个名字通过多种网络访问协议来访问资源。

URN 仍然处于试验阶段，本书中一般会不加区分地使用 URI 和 URN

## 事务

一个 HTTP 事务由一条客户端发往服务器的请求命令和一个从服务器返回的响应结果组成。这种通信是通过名为 HTTP 报文（HTTP message）的格式化数据块进行的。

![image](https://user-images.githubusercontent.com/37435717/85011260-da5c1c80-b193-11ea-8fad-f3519c01652c.png)

### 方法

每条 HTTP 请求报文都 包含一个 HTTP 方法（HTTP method），用于告诉服务器要执行什么动作。

五种常见的 HTTP 方法：

HTTP 方法 |                      描 述
:--------:|:--------------------------:
   GET    |                 从服务器向客户端
   PUT    | 将来自客户端的数据存储到一个命名的服务器资源中去
  DELETE  |              从服务器中删除命名资源
   POST   |     将客户端数据发送到一个服务器网关应用程序
   HEAD   |         仅发送命名资源响应中的 HTTP 首部

[第 3 章]() 将详细讨论 HTTP 方法

### 状态码

每个 HTTP 响应报文返回时会带一个三位数字的状态码，告知请求是否成功或需要采取其他动作。

集中常见的状态码

HTTP 状态码 |                 描 述
:----------:|:-----------------------:
    200     |            OK。文档正确返回
    302     | Redirect（重定向）。到其他地方去获取资源
    404     |  Not Found（没找到）。无法找到这个资源

状态码后还会跟一条解释性的“原因短语”文本（如[事务](#事务)图中的 OK），原因短语是为了进行描述，但所有的处理过程都是使用数字码的，如 HTTP 软件处理下列状态码和原因短语的方式是一样的

```
200 OK
200 Document attached
200 Success
200 All's cool, dude
```

[第 3 章]()将详细解释 HTTP 状态码

### Web 页面中可以包含多个对象

应用程序完成一项任务时通常会发布多个 HTTP 事务，通常一个 Web 页面不是单个资源，而是一组资源的集合

![image](https://user-images.githubusercontent.com/37435717/85013297-ebf2f380-b196-11ea-943c-e788fb9ad273.png)

## 报文

（[第 3 章]()会深入研究 HTTP 报文）

HTTP 报文由一行行的简单字符串组成，都是纯文本而不是二进制代码，人们可以方便地对其进行读写。

一个简单事务所用的 HTTP 报文

![image](https://user-images.githubusercontent.com/37435717/85014140-4ccefb80-b198-11ea-8188-ed949880ea45.png)

只有请求报文（request message）和响应报文（response message）两种报文，两者格式也很类似

HTTP 报文包括：
- **起始行**
  - 报文的第一行
  - 请求报文中用于说明要干什么
  - 响应报文用于说明出现了什么情况
- **首部字段**
  - 起始行后面由**零**个或者多个首部字段
  - 每个首部字段都包含一个用冒号（:）分隔的名值对
  - 首部以一个空行结束
- **主体**
  - 空行之后是可选的报文主体，其中包含了所有类型的数据
    - 请求主体包含要给服务器的数据，响应主体反之
  - 起始行和首部都是文本形式且结构化的，而主体中可以包含任意二进制数据或文本

例子

![image](https://user-images.githubusercontent.com/37435717/85014661-3ffed780-b199-11ea-9dbf-36f36fbcdd5f.png)

## 连接

介绍报文是如何通过 TCP（传输控制协议 Transmission Control Protocol）连接从一个地方传递到另一个地方的

### TCP/IP

HTTP 协议位于 TCP 的上层，HTTP 使用 TCP 来传输其报文数据，TCP 则位于 IP 的上层

TCP 提供了：
- 无差错的数据传输
- 按序传输
- 未分段的数据流（可以在任意时刻以任意尺寸将数据发送出去）

![image](https://user-images.githubusercontent.com/37435717/85015269-42156600-b19a-11ea-9225-cd940b532acb.png)

### 连接、IP 地址及端口号

IP（Internet Protocol）

URL `http://207.200.83.29:80/index.html` 直接指明了机器的 IP 地址以及端口号 80

URL `http://www.netscape.com:80/index.html` 使用的是域名（主机名），域名可以通过 DNS（域名服务 Domain Name Service）转换成 IP 地址

当 HTTP 的 URL 中没有端口号时，默认为 80

因此浏览器通过 HTTP 获得一个简单的 HTML 资源的过程如下：

1. 从 URL 中解析出主机名
2. 通过 DNS 转换成 IP 地址
3. 从 URL 中解析出端口号（没有时默认 80）
4. 建立与服务器的 TCP 连接
5. 向服务器发送 HTTP 请求报文
6. 服务器返回 HTTP 响应报文
7. 关闭连接，浏览器显示文档

![image](https://user-images.githubusercontent.com/37435717/85015806-37a79c00-b19b-11ea-8be8-69b469094170.png)


### 使用 Telnet 实例

Telnet 常用于远程终端绘画，几乎可以连接所有的 TCP 服务器（包括 HTTP 服务器）

## 协议版本

**HTTP/0.9**，1991 原型版本，有很多设计缺陷，只支持 GET 方法，不支持 MIME 类型、各种首部、版本号

**HTTP/1.0**，第一个广泛使用的版本。添加了版本号、首部、额外的方法、MIME 类型

**HTTP/1.0+**，20 世纪 90 年代中叶，很多 Web 客户端、服务器都在飞速向 HTTP 中添加各种特性，包括持久的 keep-alive 连接、虚拟主机支持、代理连接支持，称为非官方的事实标准

**HTTP/1.1**，重点关注校正 HTTP 设计中的结构性缺陷，明确语义，引入重要的性能优化措施，删除不好的特性，当前的主流版本

**HTTP/NG（2.0）**，重点关注性能的大幅优化，更强大的服务逻辑远程执行框架

## Web 的结构组建

### 代理

客户端和服务器之间的 HTTP 中间实体，Web 

### 缓存

HTTP 仓库，使常用页面副本保存在离客户端更近的地方

### 网关

连接其他应用程序的特殊 Web 服务器

### 隧道

对 HTTP 通信报文进行盲转发的特殊代理

### Agent 代理

发起自动 HTTP 请求的半智能 Web 客户端