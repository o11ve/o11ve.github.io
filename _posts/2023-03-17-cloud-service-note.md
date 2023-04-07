---
layout: post
title: cloud service note
subtitle: 0.o
author: Olive
categories: java cloud
tags: java cloud
date: 2023-03-17 15:00:00
---

## 服务架构

> spring-cloud-dependencies\
> spring-cloud-alibaba-dependencies

|         |                  |
|---------|------------------|
| 分布式配置   | Nacos            |
| 服务注册/发现 | Nacos            |
| 服务熔断    | Sentinel         |
| 服务调用    | Open Feign       |
| 服务路由    | Gateway          |
| 消息      | RabbitMQ & KafKa |
| 负载均衡    | Ribbon           |
| 分布式事务   | Seata            |

## 登录注册

### 1.登录

> 1. 校验短信验证码
> 2. 校验手机号
> 3. 设置、返回Token

### 2.三方登录

> 微信小程序登录步骤
> 1. **appid** 微信接口获取 **token**
> 2. **token** & **phoneCode** 微信接口获取 **phone**
> 3. **phone** 查**info**表 无匹配就新增 返回 **account**
> 4. **appId** & **code** 微信接口获取 **unionid** & **openid**
> 5. **uninoid** & **openid** & **account** 查**auth**表，有匹配修改，无匹配就新增，返回**auth**
> 6. **account** 设置且返回 **token**

> 微信app登录步骤
> 1. **appid** & **code** 微信接口获取 **openid** & **token**
> 2. **openid** & **token** 微信接口获取 **unionid** & **nickName**
> 3. **unionId** 查**auth**表 无匹配就新增 返回 **auth**
> 4. **auth** 无 **account** 返回 **authid** 处理绑定手机号
> 5. **auth** 有 **account** 设置且返回 **token**

TODO...


