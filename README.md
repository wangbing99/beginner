# 如何实现简单的用户注册&登陆&保持会话功能？

### 需求描述

* 注册功能：用户信息比较简单，注册时需要提供的信息仅为：手机号、用户名。
* 登陆功能：用户需要通过提交校验信息(如密码)实现认证并返回自己的基本信息。
* 会话功能：当用户登陆过后，一段时间内(如30分钟)在查询自己的信息时可以直接获取到；会话过期后，应提示用户需要重新登陆。
* 以上功能以接口形式实现即可，有页面更佳

### 容灾考虑

某个容器实例由于意外停止工作时，要求不影响用户的正常功能使用

### 团队规范

出于统一技术栈的考虑，我们还要求项目遵守以下规范：

场景 | 规范
------------ | -------------
工程类型 | Web 项目
语言版本 | Java 1.8
代码版本管理 | Git Without GUI
IDE | IntelliJ IDEA
类库依赖管理 | Maven
Java Web 容器 | Spring 4.0+
Web 中间件 | tomcat
Load Balance | Nginx
接口协议 | HTTP/HTTPS
数据库存储 | Mysql
数据库访问工具类 | JdbcTemplate

### 思考点

1. REST 语义
2. Spring 的 IOC 是指什么
3. Cookie 和 Session 的区别
4. Tomcat 和 Spring 都是容器，这两个容器是一个意思吗
5. Java 语言的常用容器
6. 当用户量级放大到百万级别时，瓶颈点是什么


### 接口示例

我们可以直接使用curl命令访问接口，如下是一个GET请求示例：

```shell
curl 'https://api.github.com/user/repos?page=2&per_page=100'
```

```json
{
  "message": "Requires authentication",
  "documentation_url": "https://docs.github.com/rest/reference/repos#list-repositories-for-the-authenticated-user"
}
```
