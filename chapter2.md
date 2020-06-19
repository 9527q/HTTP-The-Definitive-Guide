<h1 align="center">URL 与资源</h1>

URL 是因特网资源的标准化名称，它指向每一条电子信息，并说明其位于何处、如何交互

---

## 浏览因特网资源

URI 是统一资源标志符，分为 URL 和 URN，URL 通过描述资源位置标识资源，而 URN 通过名字识别资源，与位置无关。本书一般不加区分的使用 URI 和 URL

## URL 的语法

```
<scheme>://<user>:<password>@<host>:<port>/<path>;<params>?<query>#<frag>
```

![image](https://user-images.githubusercontent.com/37435717/85114779-261ecc80-b24d-11ea-9cef-20f5b8337a43.png)


其中最重要的是方案（scheme）、主机（host）和路径（path）

### 方案——使用什么协议

规定如何访问指定资源的主要标识符，告知解析 URL 的应用程序该使用什么协议

方案组建必须以一个字母符号开始，以第一个 `:` 符号将其与 URL 的其他部分分隔开。

大小写无关

### 主机与端口

声明提供资源的服务在哪台机器的哪个地方

可以用主机名或 IP 地址表示主机，两者是等价的。对下层使用了 TCP 协议的 HTTP 来说，默认端口号是 80

### 用户名和密码

FTP 协议一般要求输入用户名和密码，如果 URL 中没有提供，那浏览器一般会插入一个默认的用户名和密码（不同浏览器的默认密码不同，但名字可能都是 anonymous）

`@` 将用户名和密码组件与 URL 的其余部分分隔开，用户名和密码之间使用 `:` 分隔

### 路径

说明资源位于服务器的什么地方，很像一个分级的文件系统路径，端口后面的第一个 `/` 也是属于路径组件的。路径是服务器定位资源时所需的信息，可以用字符 `/` 将 HTTP URL 的路径组件规划分成一些路径段（path segment），每个路径段都有自己的参数（param）组件

### 参数

是一个名值对列表，由 `;` 将其与 URL 的其余部分（以及其余名值对）分隔开来。如

```
http://www.joes-hardware.com/hammers:sale=false/index.html;graphics=true
```

### 查询字符串

URL 的查询（query）组件和标识网关资源的 URL 路径组件一起被发送给网关资源

由一系列由 `&` 分隔的名值对组成

### 片段

某些资源可以在资源中做进一步的划分，如 HTML 重的某个章节（锚点），片段（frag）就是用来表示一个资源内部的片段的。

HTTP 服务器通常只处理整个对象，而不是对象的片段，客户端不能将片段传递给服务器。

浏览器从服务器获得了整个资源之后，再根据片段来显示你感兴趣的那部分资源

![image](https://user-images.githubusercontent.com/37435717/85116575-1e145c00-b250-11ea-8329-f5f9e61d31bc.png)

## URL 快捷方式

Web 客户端可以理解并使用集中 URL 快捷方式

### 相对 URL

相对 URL 是不完整的，需要一个被称为基础（base）的 URL 以进行解析，完整的 URL 就是绝对 URL

基础 URL 也可以是一个包含 path 的 URL，如 `http://www.joes-hardware.com/tools.html`

相对 URL 为保持一组资源的便携性提供了一种便捷方式。它只需提供相对位置即可，这样一组资源可以整体搬运而其中的相对 URL 依然有效。

**1、基础 URL**

- 资源冲显示提供。如 HTML 中的 `<BASE>` 标记
- 封装资源的基础 URL。如果在一个没有显示指定基础 URL 的资源中发现了一个相对 URL，可以将其所属资源的 URL 作为基础
- 没有基础 URL。那可能就是一个不完整或损坏了的 URL

**2、解析相对引用**

解析/分解（decomposing）URL：将 URL 划分成一个个组件

将相对 URL 转换成绝对 URL 的算法：

![image](https://user-images.githubusercontent.com/37435717/85119681-b6144480-b254-11ea-9a55-968ae49f8e46.png)

### 自动扩展 URL

在用户提交 URL 后浏览器尝试为其进行自动扩展

- 主机名扩展，如 `baidu` 自动扩展成 `www.baidu.com`
- 历史扩展，根据历史记录进行匹配

## 令人头疼的字符

URL 是可移植的（portable），设计 URL 必须保证通过任意因特网协议都能不丢失信息的**安全**传输。有些协议如 SMTP 在传输时会剥去一些特定的字符，为了避开这些问题，URL 只能使用一些相对较小的通用的安全字母表中的字母

除了安全，设计者还希望 URL 是**可读的**，因此某些不可见、不可打印字符虽然能穿过邮件程序，但不能在 URL 中使用

另外 URL 还得是**完整的**，因为有时要传递一些安全字母表之外的二进制数据或字符

### URL 字符集

从 US-ASCII 得到一个基础字符集加上转移序列

### 编码机制

通过转义表示不安全的字符。

转义格式：`%` 跟两个表示字符 ASCII 码的十六进制数，如

字符 | ASCII 码  | URL 中的表示
:---:|:---------:|:-------:
  ~  | 126(0x7E) |     %7E
空格 | 32(0x20)  |     %20
  %  | 37(0x25)  |     %25

### 字符限制

![image](https://user-images.githubusercontent.com/37435717/85125575-76525a80-b25e-11ea-9203-3278fca223f8.png)

## 方案

几个常见的方案

![image](https://user-images.githubusercontent.com/37435717/85127411-f29a6d00-b261-11ea-94d8-0950bc747be8.png)

![image](https://user-images.githubusercontent.com/37435717/85127439-ffb75c00-b261-11ea-8616-094f4289cb37.png)

更多的方案请参照[附录 A](./appendix-a.md)，或直接在 [IANA 维护的方案列表](http://www.iana.org/assignments/uri-schemes)中查看

## 未来展望

当资源移动后 URL 就不再有效。

IETF 在研究的 URN 标准可以让对象无论搬到哪里都可以提供一个稳定的名称