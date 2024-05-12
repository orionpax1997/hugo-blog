# PostgreSQL 的使用


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

```sql
CREATE USER foo WITH PASSWORD 'foo';
CREATE DATABASE foo OWNER foo;
GRANT ALL PRIVILEGES ON DATABASE foo TO foo;
```

### 提示无权限

```sql
GRANT ALL PRIVILEGES ON ALL TABLES IN SCHEMA public TO foo;
GRANT ALL PRIVILEGES ON ALL SEQUENCES IN SCHEMA public TO foo;
```

### [28000] FATAL: no pg_hba.conf entry for host

PG 数据库为了安全不会监听除了本地以外的所有请求，如果想要其他 ip 的机器访问的话需要修改 data/pg_hba.conf 文件

```conf
# IPv4 local connections:
host    all             all             127.0.0.1/32            scram-sha-256
# 添加下面这一行允许任何机器登录
host    all             all             all            scram-sha-256
# 添加下面这一行允许 192.168.1.0 到 192.168.1.255 网段登录
host    all             all             192.168.1.0/24            scram-sha-256
# 添加下面这一行允许 192.168.1.123 登录
host    all             all             192.168.1.123/32            scram-sha-256
```

