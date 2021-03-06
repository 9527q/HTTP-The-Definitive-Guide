<h1 align="center">附录 C HTTP 首部参考</h1>

当前的 HTTP/1.1 规范和官方首部及其规范描述参见 RFC 2616

---

下面的首部是根据字母顺序排序的，只给出首部名称方便查找定位，其他内容贴图

## Accept

有关内容协商和 q 值的完整讨论参见[第 17 章](./chapter17.md)

![image](https://user-images.githubusercontent.com/37435717/85195068-157c5e00-b302-11ea-9015-d029551a3fa3.png)

## Accept-Charset

有关内容协商和 q 值的完整讨论参见[第 17 章](./chapter17.md)

![image](https://user-images.githubusercontent.com/37435717/85195173-fe8a3b80-b302-11ea-8f81-a1ef9e06b9ed.png)

![image](https://user-images.githubusercontent.com/37435717/85195181-0649e000-b303-11ea-9ff3-b44e9f0583c4.png)

## Accept-Encoding

[第 17 章](./chapter17.md)讨论了 Accept-Encoding 首部

![image](https://user-images.githubusercontent.com/37435717/85195244-5d4fb500-b303-11ea-995d-ebe02e052541.png)

## Accept-Language

[第 17 章](./chapter17.md)详尽介绍了 Accept-Language 首部

![image](https://user-images.githubusercontent.com/37435717/85195265-8bcd9000-b303-11ea-9e67-e1a3837bc343.png)

## Accept-Ranges

服务器使用的

如果服务器不支持对那个资源的范围请求，可以以适当的状态码进行响应，如状态码 416（见 [3.4.4 节](./chapter3.md#400～499——客户端错误状态码)）

[第 17 章](./chapter17.md)详尽介绍了 Accept-Ranges 首部

![image](https://user-images.githubusercontent.com/37435717/85195279-b1f33000-b303-11ea-93d6-09f0e4e0b3d0.png)

## Age

更多有关 Age 首部的内容参见[第 7 章](./chapter7.md)

![image](https://user-images.githubusercontent.com/37435717/85195409-c7b52500-b304-11ea-9686-ce4464dc6741.png)

## Allow

更多关于状态码 405 的内容参见 [3.4.4 节](./chapter3.md#400～499——客户端错误状态码)

![image](https://user-images.githubusercontent.com/37435717/85195561-334bc200-b306-11ea-9a07-abf8c8cedffa.png)

![image](https://user-images.githubusercontent.com/37435717/85195590-6726e780-b306-11ea-801c-b0c1dc6ac67c.png)

## Authorization

> [ˌɔːθərəˈzeɪʃn]

有关 Authorization 首部详细内容参见[第 14 章](./chapter14.md)

![image](https://user-images.githubusercontent.com/37435717/85195611-9ccbd080-b306-11ea-9ec0-c3bf3ffcd403.png)

## Cache-Control

[第 7 章](./chapter7.md)简要介绍了缓存，并说明了与这个首部有关的特定细节

![image](https://user-images.githubusercontent.com/37435717/85195727-8f631600-b307-11ea-8b85-b187eec57333.png)

## Client-ip

> [ˈklaɪənt]

![image](https://user-images.githubusercontent.com/37435717/85195760-c6d1c280-b307-11ea-9b49-4d4dc8db457b.png)

## Connection

有关 keep-alive 和持久连接的内容参见[第 4 章](./chapter4.md)

![image](https://user-images.githubusercontent.com/37435717/85195773-d81acf00-b307-11ea-8cd1-71c923f6dcb5.png)

![image](https://user-images.githubusercontent.com/37435717/85195788-fe406f00-b307-11ea-8deb-c2bc345dcac9.png)

## Content-Base

更多有关基础 URL 的信息参见 [2.3 节](./chapter2.md#url-快捷方式)

![image](https://user-images.githubusercontent.com/37435717/85195872-8e7eb400-b308-11ea-9e74-166aa7704060.png)

## Content-Encoding

是否进行过编码

![image](https://user-images.githubusercontent.com/37435717/85195916-0a78fc00-b309-11ea-9802-a80fcadc3d9c.png)

![image](https://user-images.githubusercontent.com/37435717/85195930-2a102480-b309-11ea-9022-ae62d615bf7e.png)

## Content-Language

![image](https://user-images.githubusercontent.com/37435717/85195937-3c8a5e00-b309-11ea-8ef3-6ea66d371c5c.png)

## Content-Lenght

HEAD HTTP 请求中表示**如果**发送的话，主体会有多长

![image](https://user-images.githubusercontent.com/37435717/85195960-65125800-b309-11ea-9fdd-3878e214d4ff.png)

## Content-Location

![image](https://user-images.githubusercontent.com/37435717/85195978-86734400-b309-11ea-9934-ff8a08176b6c.png)

![image](https://user-images.githubusercontent.com/37435717/85195982-93903300-b309-11ea-9da9-c35c02fe6e55.png)

## Content-MD5

可以端到端的检查数据，但不应将其用于安全目的

MD5 摘要在 RFC 1864 中定义

![image](https://user-images.githubusercontent.com/37435717/85196003-b4588880-b309-11ea-9c09-b32aa0a1d87c.png)

## Content-Range

更多有关 Content-Range 的内容参见[第 15 章](./chapter15.md)

![image](https://user-images.githubusercontent.com/37435717/85196034-ef5abc00-b309-11ea-9beb-eed9f42f2e01.png)

## Content-Type

![image](https://user-images.githubusercontent.com/37435717/85196120-87f13c00-b30a-11ea-826f-3068551e3b48.png)

## Cookie

[第 11 章](./chapter11.md)详细讨论了 Cookie 首部及其用法

![image](https://user-images.githubusercontent.com/37435717/85196194-08b03800-b30b-11ea-8fde-b95ebd0180b1.png)

## Cookie2

[第 11 章](./chapter11.md)详细讨论了 Cookie2 首部及其用法

![image](https://user-images.githubusercontent.com/37435717/85196217-3e552100-b30b-11ea-843b-829a3b6411cb.png)

## Date

![image](https://user-images.githubusercontent.com/37435717/85196230-562ca500-b30b-11ea-87cf-42321c141369.png)

![image](https://user-images.githubusercontent.com/37435717/85196242-6cd2fc00-b30b-11ea-88ba-9ec7fcf8b58b.png)

## ETag

[第 15 章](./chapter15.md)讨论过实体标记及其与资源之间的关系

![image](https://user-images.githubusercontent.com/37435717/85196253-8411e980-b30b-11ea-9e37-547f57f56f2c.png)

## Expect

响应码 100 Continue 参见 [3.4.1 节](./chapter3.md#100～199——信息性状态码)

![image](https://user-images.githubusercontent.com/37435717/85196271-aefc3d80-b30b-11ea-8716-ec0c4bdd2e63.png)

## Expires

[第 7 章](./chapter7.md)讨论过 Expires 首部用法

![image](https://user-images.githubusercontent.com/37435717/85196377-89bbff00-b30c-11ea-8a2d-e10f701a4af2.png)

## From

![image](https://user-images.githubusercontent.com/37435717/85196404-ac4e1800-b30c-11ea-8b25-e5bc4ad8ae76.png)

## Host

![image](https://user-images.githubusercontent.com/37435717/85196436-cee03100-b30c-11ea-86af-e4b917f4f7cf.png)

## If-Modified-Since

[第 7 章](./chapter7.md)详细讨论了条件请求

![image](https://user-images.githubusercontent.com/37435717/85196460-eb7c6900-b30c-11ea-8a34-fd41806c1c4c.png)

## If-Match

[第 7 章](./chapter7.md)讨论了条件请求

![image](https://user-images.githubusercontent.com/37435717/85196484-15359000-b30d-11ea-8f32-94f968b12ad3.png)

## If-None-Match

[第 7 章](./chapter7.md)讨论了条件请求

![image](https://user-images.githubusercontent.com/37435717/85196500-326a5e80-b30d-11ea-908e-c28df880917b.png)

## If-Range

[第 7 章](./chapter7.md)讨论了条件请求

![image](https://user-images.githubusercontent.com/37435717/85196564-94c35f00-b30d-11ea-888a-1841ae367a05.png)

## If-Unmodified-Since

[第 7 章](./chapter7.md)讨论了条件请求

![image](https://user-images.githubusercontent.com/37435717/85196607-d48a4680-b30d-11ea-8263-7b6f12a2812f.png)

![image](https://user-images.githubusercontent.com/37435717/85196610-da802780-b30d-11ea-8dae-314f7e341716.png)

## Last-Modified

![image](https://user-images.githubusercontent.com/37435717/85196621-07343f00-b30e-11ea-9961-1cbaf3cab021.png)

## Location

![image](https://user-images.githubusercontent.com/37435717/85196630-2501a400-b30e-11ea-8b08-8b909cd6c10a.png)

## Max-Forwards

更多有关 TRACE 方法的信息参见 3.3 节

![image](https://user-images.githubusercontent.com/37435717/85196641-38ad0a80-b30e-11ea-9674-fb07253080c1.png)

![image](https://user-images.githubusercontent.com/37435717/85196668-67c37c00-b30e-11ea-9c6c-2a67ac43c375.png)
