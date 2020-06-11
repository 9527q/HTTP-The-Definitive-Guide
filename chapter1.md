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

**MIME 类型**（MIME type）（MIME：Multipurpose Internet Mail Extension，多用途因特网邮件扩展）发源于电子邮件系统，又被 HTTP 采纳以标记因特网上各种不同数据类型的多媒体内容。

> [maɪm]

Web 服务器会为所有 HTTP 对象数据附加一个 MIME 类型。Web 浏览器取回对象时会去查看相关的 MIME 类型，看是否知道应该如何处理这个对象。

![MIME 类型的返回](https://user-images.githubusercontent.com/37435717/84217132-ea259200-aafd-11ea-8dd7-a97b4ecdf963.png)

MIME 类型是一种文本标记，由主类型和子类型构成，中间由斜杠分隔。如 HTML 文档为 `text/html`；ASCII 文档为 `text/plain`；GIF 图片为 `image/gif`。[附录 D](./appendix-d.md) 提供了完整的 MIME 类型。

