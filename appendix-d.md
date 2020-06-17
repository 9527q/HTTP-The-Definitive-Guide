<h1 align="center">MIME 媒体类型</h1>

MIME 类型是描述报文实体主题内容的一些标准化名称。

这个附录说明了 MIME 类型工作方式、如何注册新的类型、去哪里查找更多相关信息

---

## 背景知识

MIME 类型最初是为多媒体电子邮件而开发的（Multipurpose Internet Mail Extension，多用途因特网邮件扩展）

MIME 主要由下列 5 份文档定义（RFC 2045～2049）

- RFC 2045，描述了 MIME 报文结构概况，介绍了 HTTP 借用的 Content-Type 首部
- RFC 2046，介绍了 MIME 类型及其结构
- RFC 2047，定义了一些在首部包含非 ASCII 字符的方式
- RFC 2048，如何向 IANA（因特网号码分配机构 Internet Assigned Numbers Authority） 注册 MIME 值
- RFC 2049，详细介绍一致性规则和实例

> RFC: 请求意见稿（英语：Request for Comments，缩写：RFC）是由互联网工程任务组（IETF）发布的一系列备忘录。文件收集了有关互联网相关信息，以及UNIX和互联网社群的软件文件，以编号排定。目前RFC文件是由互联网协会（ISOC）赞助发行。[维基百科](https://zh.wikipedia.org/wiki/RFC)

## MIME 类型结构

结构：`<类型>/<子类型>[; <可选参数>]`

- 类型和自类型以 `/` 分隔
- 若有可选参数，则以 `;` 开始（没有参数时不加 `;`）

在 HTTP 中，MIME 媒体类型被用于 Content-Type 和 Accept 首部。例如

```
Content-Type: video/quicktime
Content-Type: text/html; charset="iso-8859-6"
Content-Type: multipart/mixed; boundary=gc0prJq0M2Yt08j34c0p
Accept: image/gif
```

### 离散类型（discrete type）

MIME 类型可以直接用于描述对象类型，也可以描述其他对象类型的集合或类型包。如果直接用于描述某个类型，就是一种离散类型。

### 复合类型（composite type）

如果描述的是其他内容的集合或封装包，就被称为复合类型

### 多部分类型

多部分媒体类型是复合类型。包含多个组建类型，每个组建都有自己的 MIME 类型。例如：

![image](https://user-images.githubusercontent.com/37435717/84850976-ba413600-b08b-11ea-94cb-ec3859aab902.png)

使用 `multipart/mixed` 声明是多部分类型，通过参数 `boundary` 指定分界标志。

各部分内容分隔标志：每个【`--` + 分界标志】都表示一部分内容的开始，【`--` + 分界标志 + `--`】表示整个的结束。

每部分内容的开头都标记了 `Content-type`，其内容还可以是多部分类型的（当然也可以是离散类型的），不过其自内容是有缩进的，分隔标志是没有缩进的。

### 语法

主要由主类型、子类型和可选参数列表组成

**主类型**可以是预定义类型、IETF 定义的扩展标记，或者实验性标记（以“x-”开头）

常见的主类型：application、audio、chemical、image、message、model、multipart、text、video

![image](https://user-images.githubusercontent.com/37435717/84851281-73077500-b08c-11ea-9f62-fbe5ccc01b2b.png)

**子类型**可以是主类型（如 `text/text`）、IANA 注册的子类型、实验性扩展标记（以 `x-` 开头）

类型和子类型都是由 US-ASCII 字符的子集构成。空格和某些保留分组以及标点符号称为 “tspecials”，是控制字符，不用于类型和子类型。

RFC 2046 定义的语法：

![image](https://user-images.githubusercontent.com/37435717/84851879-fe353a80-b08d-11ea-8cab-55a3d5cf0cb2.png)

## 在 IANA 注册 MIME 类型

RFC 2048

书中还讲了注册过程、注册规则、注册模板、MIME 媒体类型注册，这里不做记录

### 注册树

四种 MIME 类型各有自己的注册规则

![image](https://user-images.githubusercontent.com/37435717/84851980-43596c80-b08e-11ea-8f91-6b3b5600d196.png)

## MIME 类型表

直接贴图过来，方便以后查找，表中的内容是按照字母顺序排序的

### application/*

![image](https://user-images.githubusercontent.com/37435717/84852528-b0b9cd00-b08f-11ea-8c38-63b8c1d89c26.png)

![image](https://user-images.githubusercontent.com/37435717/84852705-1312cd80-b090-11ea-9f01-055efcca8c6b.png)

![image](https://user-images.githubusercontent.com/37435717/84852808-58cf9600-b090-11ea-8d4e-b17791e327cd.png)

![image](https://user-images.githubusercontent.com/37435717/84852904-92a09c80-b090-11ea-90e7-cede1785af6c.png)

![image](https://user-images.githubusercontent.com/37435717/84853094-f75bf700-b090-11ea-8875-6ab01e05f96c.png)

![image](https://user-images.githubusercontent.com/37435717/84853621-29ba2400-b092-11ea-945f-1ade287fa41e.png)

![image](https://user-images.githubusercontent.com/37435717/84853757-74d43700-b092-11ea-8fab-e93282a5e904.png)

![image](https://user-images.githubusercontent.com/37435717/84853790-8f0e1500-b092-11ea-9249-42de0a83be15.png)

![image](https://user-images.githubusercontent.com/37435717/84861209-1c596580-b0a3-11ea-8119-46c8dc923cb5.png)

![image](https://user-images.githubusercontent.com/37435717/84861258-36934380-b0a3-11ea-9a37-31561b8940b6.png)

![image](https://user-images.githubusercontent.com/37435717/84861295-4f035e00-b0a3-11ea-9330-eb607ecb2811.png)

![image](https://user-images.githubusercontent.com/37435717/84861355-68a4a580-b0a3-11ea-9520-194271b3a84b.png)

### audio/*

![image](https://user-images.githubusercontent.com/37435717/84861413-8f62dc00-b0a3-11ea-9540-ba50c575ec10.png)

![image](https://user-images.githubusercontent.com/37435717/84861435-9f7abb80-b0a3-11ea-8442-4ceb8bcfe42f.png)

![image](https://user-images.githubusercontent.com/37435717/84861468-aefa0480-b0a3-11ea-925d-c643987d2254.png)

### chemical/*

![image](https://user-images.githubusercontent.com/37435717/84861583-f8e2ea80-b0a3-11ea-861c-40d1682567f1.png)

![image](https://user-images.githubusercontent.com/37435717/84861614-0dbf7e00-b0a4-11ea-8431-ff580dbea1f7.png)

### image/*

![image](https://user-images.githubusercontent.com/37435717/84861681-334c8780-b0a4-11ea-856c-bd62361e6c16.png)

### message/*

![image](https://user-images.githubusercontent.com/37435717/84861862-99d1a580-b0a4-11ea-95c0-41b379ae4985.png)

### model/*

![image](https://user-images.githubusercontent.com/37435717/84862018-f8971f00-b0a4-11ea-9a36-0a0e72876792.png)

![image](https://user-images.githubusercontent.com/37435717/84862027-00ef5a00-b0a5-11ea-8f25-41db0cef345b.png)

### multipart/*

![image](https://user-images.githubusercontent.com/37435717/84862324-8a069100-b0a5-11ea-9f0d-852fffc8b7ad.png)

![image](https://user-images.githubusercontent.com/37435717/84862354-9854ad00-b0a5-11ea-969f-9e3fc2ebac32.png)

### text/*

![image](https://user-images.githubusercontent.com/37435717/84862411-b7533f00-b0a5-11ea-9646-163f128bb315.png)

![image](https://user-images.githubusercontent.com/37435717/84862512-e4075680-b0a5-11ea-80e2-c41fb2b5597e.png)

![image](https://user-images.githubusercontent.com/37435717/84862536-eff31880-b0a5-11ea-8ef8-017d23ec8111.png)

### video/*

![image](https://user-images.githubusercontent.com/37435717/84862606-08fbc980-b0a6-11ea-8ecb-e4620902273c.png)

![image](https://user-images.githubusercontent.com/37435717/84862998-c1c20880-b0a6-11ea-8e48-ed65ecef5960.png)

### 实验类型

![image](https://user-images.githubusercontent.com/37435717/84864259-f9ca4b00-b0a8-11ea-9b42-2dfaf7478831.png)
