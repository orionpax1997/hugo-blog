---
title: "Hibernate 的使用"
date: 2019-07-23T21:37:28+08:00
categories: ["Development"]
tags: ["Backend Framework"]
featuredImage: "https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/Development/hibernate-banner.h62ovuf51h4.webp"
---

## 简介

> Hibernate 是一种 ORM 框架，全称为 Object_Relative DateBase-Mapping，在 Java 对象与关系数据库之间建立某种映射，以实现直接存取 Java 对象！

## 基础

{{< card "https://segmentfault.com/a/1190000013568216" >}}
{{< card "https://www.liaoxuefeng.com/wiki/1252599548343744/1266263275862720" >}}

## 应用场景

### 如何处理 Hibernate 多线程下 No Session 问题?

#### 问题描述

Hibernate 使用多线程，且在线程内部获取对象懒加载的属性就会出现 No Session。

#### 产生原因

其他线程并未获取到 Session。

#### 解决方式

```java
// 解决方法1

public static boolean bindHibernateSessionToThread(SessionFactory sessionFactory) {
    if (TransactionSynchronizationManager.hasResource(sessionFactory)) {
        return true;
    } else {
        Session session = sessionFactory.openSession();
        session.setFlushMode(FlushMode.MANUAL);
        SessionHolder sessionHolder = new SessionHolder(session);
        TransactionSynchronizationManager.bindResource(sessionFactory, sessionHolder);
    }
    return false;
}

// 将线程上绑定的Session关闭
public static void closeHibernateSessionFromThread(boolean participate, Object sessionFactory) {
    if (!participate) {
        SessionHolder sessionHolder = (SessionHolder)TransactionSynchronizationManager.unbindResource(sessionFactory);
        SessionFactoryUtils.closeSession(sessionHolder.getSession());
    }
}

//使用(注意在线程中使用的对象要是在线程中查出来的，不能是查出来再开线程)
SessionFactory sessionFactory = ContextHolder.getBean(SessionFactory.class);
boolean participate = ConcurrentUtil.bindHibernateSessionToThread(sessionFactory);
//...Method
ConcurrentUtil.closeHibernateSessionFromThread(participate, sessionFactory);
```

```
// 解决方法2
// 配置 Hibernate Lazy="false"
```
