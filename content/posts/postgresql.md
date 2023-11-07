---
title: "PostgreSQL 的使用"
date: 2022-08-31T14:56:46+08:00
categories: ["Development"]
tags: ["Support"]
---

## 简介

> 现在称为 PostgreSQL 的对象关系数据库管理系统源自加州大学伯克利分校编写的 POSTGRES 包。经过二十多年的发展，PostgreSQL 现在是世界上最先进的开源数据库。

{{< card "https://www.postgresql.org/docs/current/preface.html" >}}

## 安装

```shell
docker pull postgres
docker run --name postgres -p 5432:5432 -e POSTGRES_PASSWORD=yoursecretpassword -d postgres
```

## 应用场景

### 创建数据库、用户并且赋权

```shell
CREATE USER foo WITH PASSWORD 'foo';
CREATE DATABASE foo OWNER foo;
GRANT ALL PRIVILEGES ON DATABASE foo TO foo;
```
