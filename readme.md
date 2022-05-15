## 项目简介

该项目采用springboot fluxWeb,r2dbc等响应式组件，是个人学习的一次响应式实践

实现了短链系统的核心功能。

### 环境信息

- mysql 8.0.29
- Springboot 2.6.7
- JDK 8

## api简介

### 【post】/hash/shortUrl

请求参数类型：multipart/form-data

请求参数:

|参数|说明|
|--|--|
|url|需要转换的长链|

该接口负责将长链转换为短链。

返回参数

|参数|说明|
|--|--|
|id||
|shortUrl|短链地址标识|
|shortUrlInt|短链地址对应的10进制表示|
|targetUrl|对应的长链地址|

### 【get】/{shortUrl}

请求参数类型：path

|参数||
|--|--|
|shortUrl|短链地址标识|

<br/>

例子 ，127.0.0.1/短链地址标识

> 127.0.0.1/短链地址标识  即为完整的短链地址

<br/>

### 【get】/show/real/count

一个实时推送系统当前访问量的接口，每隔十秒推送一次，推送的数据为每分钟内0s、10s、20s、30s、40s、50s、间隔内的访问量。

直接在浏览器访问即可看到效果