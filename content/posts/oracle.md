---
title: "Oracle 的使用"
date: 2021-10-09T20:36:44+08:00
categories: ["Development"]
tags: ["Support"]
featuredImage: "https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/Development/oracle-banner.1s81s4rls7b4.webp"
---

## 简介

> Oracle Database，又名 Oracle RDBMS，简称 Oracle。是甲骨文公司推出的一款关系数据库管理系统。

> Oracle 数据库系统是目前世界上流行的关系数据库管理系统，拥有可移植性好、使用方便、功能强等优点，在各类大、中、小、微机环境中都适用。

> Oracle 是一种高效率、可靠性好的、适应高吞吐量的数据库解决方案。

## 入门

{{< card "https://juejin.cn/post/6844903822913978381" >}}

## 安装

### Docker 安装开发环境 Oracle 11g

{{< card "https://www.hangge.com/blog/cache/detail_2797.html" >}}

## 扩展

### Oracle number 对应 Java 数据类型

![Oracle-number-对应-Java-数据类型](https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/Development/Oracle-number-对应-Java-数据类型.16a2mb8efgww.webp "Oracle-number-对应-Java-数据类型")

## 应用场景

### 查看表字段数据结构

```sql
SELECT UTC.COLUMN_NAME, DATA_TYPE, DATA_LENGTH, COMMENTS
FROM USER_TAB_COLUMNS UTC
 LEFT JOIN USER_COL_COMMENTS UCC ON UTC.TABLE_NAME = UCC.TABLE_NAME AND UTC.COLUMN_NAME = UCC.COLUMN_NAME
WHERE UTC.TABLE_NAME = 'TABLE_NAME'
ORDER BY COLUMN_ID;
```

### Oracle 创建用户，表空间并授权

```sql
-- 查询表空间物理路径
select * from sys.DBA_DATA_FILES;
-- 创建表空间
create tablespace FOO
datafile '/home/oracle/app/oracle/oradata/helowin/FOO01.dbf'
size 50M autoextend on next 50M;
-- 创建用户绑定表空间
create user FOO identified by FOO
default tablespace FOO;
-- 授权
grant connect,resource to FOO;
grant create any sequence to FOO;
grant create any table to FOO;
grant delete any table to FOO;
grant insert any table to FOO;
grant select any table to FOO;
grant unlimited tablespace to FOO;
grant execute any procedure to FOO;
grant update any table to FOO;
grant create any view to FOO;
grant imp_full_database to FOO;
```

### Oracle 删除用户、关联数据及其表空间

```sql
DROP USER USERNAME CASCADE;
DROP TABLESPACE USERNAME INCLUDING CONTENTS AND DATAFILES;
```

### Oracle 导出导入数据

```bash
# exp 和 imp 的简单使用
exp user/pwd@sid owner=user file=file.dmp log=exp.log feedback=1000
imp user/pwd@sid fromuser=user touser=user file=file.dmp log=imp.log feedback=1000
```

#### exp 参数说明

| 参数名               | 说明                       | 默认值       |
| -------------------- | -------------------------- | ------------ |
| USERID               | 用户名/口令                |              |
| FULL                 | 导出整个文件               | N            |
| BUFFER               | 数据缓冲区的大小           |              |
| OWNER                | 导出指定的所有者用户名列表 |              |
| FILE                 | 输出文件                   | (EXPDAT.DMP) |
| TABLES               | 导出指定的表名列表         |              |
| COMPRESS             | 是否压缩导出的文件         | Y            |
| RECORDLENGTH         | IO  记录的长度             |              |
| GRANTS               | 导出权限                   | Y            |
| INCTYPE              | 增量导出类型               |              |
| INDEXES              | 导出索引                   | Y            |
| RECORD               | 跟踪增量导出               | Y            |
| ROWS                 | 导出数据行                 | Y            |
| PARFILE              | 参数文件名                 |              |
| CONSTRAINTS          | 导出限制                   | Y            |
| CONSISTENT           | 交叉表一致性               |              |
| LOG                  | 屏幕输出的日志文件         |              |
| STATISTICS           | 分析对象(ESTIMATE)         |              |
| DIRECT               | 直接路径                   | N            |
| TRIGGERS             | 导出触发器                 | Y            |
| FEEDBACK             | 显示每  x  行  (0)  的进度 |              |
| FILESIZE             | 各转储文件的最大尺寸       |              |
| QUERY                | 选定导出表子集的子句       |              |
| TRANSPORT_TABLESPACE | 导出可传输的表空间元数据   | N            |
| TABLESPACES          | 导出指定的表空间列表       |              |

#### imp 参数说明

| 参数名                | 说明                           | 默认值       |
| --------------------- | ------------------------------ | ------------ |
| USERID                | 用户名/口令                    |              |
| FULL                  | 导入整个文件                   | N            |
| BUFFER                | 数据缓冲区大小                 |              |
| FROMUSER              | 所有人用户名列表               |              |
| FILE                  | 输入文件                       | (EXPDAT.DMP) |
| TOUSER                | 用户名列表                     |              |
| SHOW                  | 只列出文件内容                 | N            |
| TABLES                | 表名列表                       |              |
| IGNORE                | 忽略创建错误                   | N            |
| RECORDLENGTH          | IO 记录的长度                  |              |
| GRANTS                | 导入权限                       | Y            |
| INCTYPE               | 增量导入类型                   |              |
| INDEXES               | 导入索引                       | Y            |
| COMMIT                | 提交数组插入                   | N            |
| ROWS                  | 导入数据行                     | Y            |
| PARFILE               | 参数文件名                     |              |
| LOG                   | 屏幕输出的日志文件             |              |
| CONSTRAINTS           | 导入限制                       | Y            |
| DESTROY               | 覆盖表空间数据文件             | N            |
| INDEXFILE             | 将表/索引信息写入指定的文件    |              |
| SKIP_UNUSABLE_INDEXES | 跳过不可用索引的维护           | N            |
| FEEDBACK              | 每  x  行显示进度              |              |
| TOID_NOVALIDATE       | 跳过指定类型  ID  的验证       |              |
| FILESIZE              | 每个转储文件的最大大小         |              |
| STATISTICS            | 始终导入预计算的统计信息       |              |
| RESUMABLE             | 在遇到有关空间的错误时挂起     |              |
| RESUMABLE_NAME        | 用来标识可恢复语句的文本字符串 |              |
| RESUMABLE_TIMEOUT     | RESUMABLE  的等待时间          |              |
| COMPILE               | 编译过程,  程序包和函数        | Y            |
| STREAMS_CONFIGURATION | 导入  Streams  的一般元数据    | Y            |
| STREAMS_INSTANITATION | 导入  Streams  的实例化元数据  | N            |
| TRANSPORT_TABLESPACE  | 导入可传输的表空间元数据       |              |
| TABLESPACES           | 将要传输到数据库的表空间       |              |
| DATAFILES             | 将要传输到数据库的数据文件     |              |
| TTS_OWNERS            | 拥有可传输表空间集中数据的用户 |              |

{{< card "https://blog.51cto.com/u_15349616/3717558" >}}
{{< card url="https://zhuanlan.zhihu.com/p/59838643" title="EXP-00091错误的说明和解决方法" description="我们在做EXP的过程中可能经常会遇到EXP-00091 Exporting questionable statistics的错误。其实这个是EXP的error message，它产生的原因是因为我们EXP工具所在的环境变量中的NLS_LANG和Database中的NLS_CHARACTERSET不一致导致的。但需要说明的是，EXP-00091这个error message对所产生的dump没有影响，生成的dump还可以正常的imp（但是最好还是再次EXP）" image="https://pic2.zhimg.com/v2-a53edf10c60cfb5477209f04ca1c58b6_720w.jpg?source=172ae18b">}}
{{< card "http://blog.itpub.net/7353848/viewspace-691312/" >}}
{{< card "https://www.codenong.com/cs106541457/" >}}
{{< card "https://www.cnblogs.com/yichong/p/9234265.html" >}}

### 锁表问题处理

```sql
-- 查询锁表信息
SELECT SESS.SID,SESS.SERIAL#, LO.ORACLE_USERNAME,LO.OS_USER_NAME, AO.OBJECT_NAME,LO.LOCKED_MODE  FROM V$LOCKED_OBJECT LO,DBA_OBJECTS AO,V$SESSION SESS WHERE AO.OBJECT_ID=LO.OBJECT_ID AND LO.SESSION_ID=SESS.SID;
-- 杀死锁表的 SESSION
ALTER SYSTEM KILL SESSION 'SID,SERIAL';
```

### 如何将逗号分隔的值字符串拆分为 Oracle 数据库中的行

{{< card title="How to split comma separated value strings into rows in Oracle Database" url="https://blogs.oracle.com/sql/post/split-comma-separated-values-into-rows-in-oracle-database" >}}
