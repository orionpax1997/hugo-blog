---title: "通过 Spring Initializr 了解常用后端框架"
date: 2021-02-14T16:45:54+08:00
categories: ["Development"]
tags: ["Backend Framework"]
featuredImage: "https://cdn.statically.io/gh/orionpax1997/picx-images-hosting@master/Development/spring-initializr-banner.5jcrfnfqm400.webp"
---

## 简介

> [Spring Initializr](https://start.spring.io/) 从本质上来说就是一个 Web 应用程序，它能为你生成 Spring Boot 项目结构。虽然不能生成应用程序代码，但它能为你提供一个基本的项目结构，以及一个用于构建代码的 Maven 或 Gradle 构建说明文件。你只需要写应用程序的代码就好了。

{{< card "https://start.spring.io/" >}}
{{< card url="https://spring.io/guides" title="Spring Guides" description="Whatever you're building, these guides are designed to get you productive as quickly as possible – using the latest Spring project releases and techniques as recommended by the Spring team.">}}
{{< card "https://spring.io/projects/spring-boot" >}}
{{< card "https://www.springcloud.cc/spring-boot.html" >}}

## Developer Tools

### Spring Native

Incubating support for compiling Spring applications to native executables using the GraalVM native-image compiler.  
孵化支持使用 GraalVM 原生映像编译器将 Spring 应用程序编译为本机可执行文件。

_还是实验期，目前不建议使用_

### Spring Boot DevTools

Provides fast application restarts, LiveReload, and configurations for enhanced development experience.  
提供快速的应用程序重启、LiveReload 和配置以增强开发体验。

_使用 IDEA 自带的热部署或者去使用 JRebel，总是你更好的选择_

### Lombok

Java annotation library which helps to reduce boilerplate code.  
Java 注释库，有助于减少样板代码。

{{< card "https://blog.dramacat.top/lombok/" >}}

### Spring Configuration Processor

Generate metadata for developers to offer contextual help and "code completion" when working with custom configuration keys (ex.application.properties/.yml files).  
给自定义的配置类生成元数据信息，可以在你编写配置文件时，对自定义的配置提供提示。

{{< card "https://docs.spring.io/spring-boot/docs/current/reference/html/configuration-metadata.html#configuration-metadata.annotation-processor" >}}
{{< card "https://matthung0807.blogspot.com/2020/09/spring-boot-configuration-processor.html" >}}
{{< card "https://www.freesion.com/article/8342995481/" >}}

## Web

### Spring Web

Build web, including RESTful, applications using Spring MVC. Uses Apache Tomcat as the default embedded container.  
使用 Spring MVC 构建 Web（包括 RESTful）应用程序。 使用 Apache Tomcat 作为默认的嵌入式容器。

{{< card "https://spring.io/guides/gs/rest-service/" >}}
{{< card "https://spring.io/guides/gs/consuming-rest/" >}}

### Spring Reactive Web

Build reactive web applications with Spring WebFlux and Netty.  
使用 Spring WebFlux 和 Netty 构建响应式 Web 应用程序。

{{< card "https://spring.io/guides/gs/reactive-rest-service/" >}}

### Spring for GraphQL

Build GraphQL applications with Spring for GraphQL and GraphQL Java.  
使用 Spring for GraphQL 和 GraphQL Java 构建 GraphQL 应用程序。

_目前没看到什么，完整的最佳实践，让子弹再飞一会吧_

{{< card "https://graphql.cn" >}}
{{< card "https://docs.spring.io/spring-graphql/docs/current-SNAPSHOT/reference/html/" >}}

### Rest Repositories

Exposing Spring Data repositories over REST via Spring Data REST.  
通过 Spring Data REST 在 REST 上公开 Spring Data 存储库。

{{< card "https://spring.io/guides/gs/accessing-data-rest/" >}}

### Spring Session

Provides an API and implementations for managing user session information.  
提供用于管理用户会话信息的 API 和实现。

{{< card "https://github.com/xkcoding/spring-boot-demo/tree/master/demo-session" >}}

### Rest Repositories HAL Explorer

Browsing Spring Data REST repositories in your browser.  
在浏览器中浏览 Spring Data REST 存储库。

{{< card title="Spring REST and HAL Browser" description="In this tutorial, we'll be discussing what HAL is and why it's useful, before introducing the HAL browser." url="https://www.baeldung.com/spring-rest-hal" >}}
{{< card "https://rwcbook.github.io/hal-forms/" >}}

### Spring HATEOAS

Eases the creation of RESTful APIs that follow the HATEOAS principle when working with Spring / Spring MVC.  
在使用 Spring / Spring MVC 时，简化遵循 HATEOAS 原则的 RESTful API 的创建。

{{< card "https://spring.io/guides/gs/rest-hateoas/" >}}
{{< card "https://restfulapi.net/hateoas/" >}}

### Spring Web Services

Facilitates contract-first SOAP development. Allows for the creation of flexible web services using one of the many ways to manipulate XML payloads.  
促进契约优先的 SOAP 开发。允许使用多种操作 XML 有效负载的方法之一创建灵活的 Web 服务。

{{< card "https://spring.io/guides/gs/producing-web-service/" >}}
{{< card "https://spring.io/guides/gs/consuming-web-service/" >}}
{{< card title="Web Services 教程" description="通过使用 Web Services，您的应用程序可以向全世界发布信息，或提供某项功能。" url="https://www.runoob.com/webservices/webservices-tutorial.html" >}}

### Jersey

Framework for developing RESTful Web Services in Java that provides support for JAX-RS APIs.  
用于在 Java 中开发 RESTful Web 服务的框架，提供对 JAX-RS API 的支持。

_你总是会选择使用 Spring Web_

### Vaadin

A web framework that allows you to write UI in pure Java without getting bogged down in JS, HTML, and CSS.  
一个 Web 框架，允许您使用纯 Java 编写 UI，而不会陷入 JS、HTML 和 CSS 的困境。

_从一个困境到另一个困境？_

## Template Engines

_模版引擎就是模版引擎，绝对不要把它们当成前端框架_

{{< card "https://springhow.com/spring-boot-template-engines-comparison/" >}}

### Thymeleaf

A modern server-side Java template engine for both web and standalone environments. Allows HTML to be correctly displayed in browsers and as static prototypes.  
适用于 Web 和独立环境的现代服务器端 Java 模板引擎。允许 HTML 在浏览器中正确显示并作为静态原型。

_可能的话，前后端分离总是你更好的选择_

{{< card "https://spring.io/guides/gs/serving-web-content/" >}}

### Apache Freemarker

Java library to generate text output (HTML web pages, e-mails, configuration files, source code, etc.) based on templates and changing data.  
Java 库，用于根据模板和变化的数据生成文本输出（HTML 网页、电子邮件、配置文件、源代码等）。

_如果一定要用的话，使用 Thymeleaf 作为的你的模版引擎_

### Mustache

Logic-less Templates. There are no if statements, else clauses, or for loops. Instead there are only tags.  
无逻辑模板。没有 if 语句、else 子句或 for 循环。相反，只有标签。

_如果一定要用的话，使用 Thymeleaf 作为的你的模版引擎_

### Groovy Templates

Groovy templating engine.  
Groovy 模板引擎。

_如果一定要用的话，使用 Thymeleaf 作为的你的模版引擎_

## Security

### Spring Security

Highly customizable authentication and access-control framework for Spring applications.  
用于 Spring 应用程序的高度可定制的身份验证和访问控制框架。

{{< card "https://docs.spring.io/spring-security/reference/index.html" >}}
{{< card title="Security with Spring" description="The Security with Spring tutorials focus, as you'd expect, on Spring Security." url="https://www.baeldung.com/security-spring" >}}

### OAuth2 Client

Spring Boot integration for Spring Security's OAuth2/OpenID Connect client features.  
Spring Security 的 OAuth2/OpenID Connect 客户端功能的 Spring Boot 集成。

{{< card "https://spring.io/guides/tutorials/spring-boot-oauth2/" >}}
{{< card title="OAuth 2.0 的一个简单解释" description="OAuth 2.0 是目前最流行的授权机制，用来授权第三方应用，获取用户数据。" url="https://www.ruanyifeng.com/blog/2019/04/oauth_design.html" >}}

### OAuth2 Resource Server

Spring Boot integration for Spring Security's OAuth2 resource server features.  
Spring Security 的 OAuth2 资源服务器功能的 Spring Boot 集成。

{{< card title="OAuth 2.0 Resource Server With Spring Security 5" url="https://www.baeldung.com/spring-security-oauth-resource-server" >}}
{{< card title="JSON Web Token 入门教程" description="JSON Web Token（缩写 JWT）是目前最流行的跨域认证解决方案，本文介绍它的原理和用法。" url="https://www.ruanyifeng.com/blog/2018/07/json_web_token-tutorial.html" >}}

### Spring LDAP

Makes it easier to build Spring based applications that use the Lightweight Directory Access Protocol.  
使构建使用轻量级目录访问协议的基于 Spring 的应用程序变得更加容易。

{{< card "https://spring.io/guides/gs/authenticating-ldap/" >}}
{{< card "https://ldap.com/learn-about-ldap/" >}}

### Okta

Okta specific configuration for Spring Security/Spring Boot OAuth2 features. Enable your Spring Boot application to work with Okta via OAuth 2.0/OIDC.  
用于 Spring Security/Spring Boot OAuth2 功能的 Okta 特定配置。使您的 Spring Boot 应用程序能够通过 OAuth 2.0/OIDC 与 Okta 一起使用。

{{< card title="Spring Security With Okta" description="Okta provides features like authentication, authorization, and social login for web, mobile, or API services. Additionally, it has robust support for the Spring Framework to make integrations quite straightforward." url="https://www.baeldung.com/spring-security-okta" >}}

## SQL

### JDBC API

Database Connectivity API that defines how a client may connect and query a database.  
定义客户端如何连接和查询数据库的数据库连接 API。

{{< card "https://spring.io/guides/gs/relational-data-access/" >}}

### Spring Data JDBC

Persist data in SQL stores with plain JDBC using Spring Data.  
使用 Spring Data 使用纯 JDBC 将数据持久存储在 SQL 存储中。

{{< card "https://docs.spring.io/spring-data/jdbc/docs/current/reference/html/" >}}

### Spring Data JPA

Persist data in SQL stores with Java Persistence API using Spring Data and Hibernate.  
使用 Spring Data 和 Hibernate 使用 Java Persistence API 在 SQL 存储中持久化数据。

{{< card "https://spring.io/guides/gs/accessing-data-jpa/" >}}

### Spring Data R2DBC

Provides Reactive Relational Database Connectivity to persist data in SQL stores using Spring Data in reactive applications.  
提供反应式关系数据库连接，以便在反应式应用程序中使用 Spring Data 将数据持久保存在 SQL 存储中。

{{< card "https://spring.io/guides/gs/accessing-data-r2dbc/" >}}

### MyBatis Framework

Persistence framework with support for custom SQL, stored procedures and advanced mappings. MyBatis couples objects with stored procedures or SQL statements using a XML descriptor or annotations.  
使用 MyBatis 的持久化支持。

{{< card "https://mybatis.org/mybatis-3/zh/index.html" >}}
{{< card "https://blog.dramacat.top/mybatis/" >}}

### Liquibase Migration

Liquibase database migration and source control library.  
Liquibase 数据库迁移和源代码控制库。

{{< card "https://docs.liquibase.com/install/home.html" >}}

### Flyway Migration

Version control for your database so you can migrate from any version (incl. an empty database) to the latest version of the schema.  
数据库的版本控制，以便您可以从任何版本（包括空数据库）迁移到架构的最新版本。

{{< card "https://flywaydb.org/documentation/" >}}

### JOOQ Access Layer

Generate Java code from your database and build type safe SQL queries through a fluent API.  
从您的数据库生成 Java 代码并通过流畅的 API 构建类型安全的 SQL 查询。

{{< card "https://www.jooq.org/doc/3.17/manual-single-page/" >}}

### IBM DB2 Driver

A JDBC driver that provides access to IBM DB2.  
提供对 IBM DB2 的访问的 JDBC 驱动程序。

### Apache Derby Database

An open source relational database implemented entirely in Java.  
一个完全用 Java 实现的开源关系数据库。

_我选 H2_

### H2 Database

Provides a fast in-memory database that supports JDBC API and R2DBC access, with a small (2mb) footprint. Supports embedded and server modes as well as a browser based console application.  
提供支持 JDBC API 和 R2DBC 访问的快速内存数据库，占用空间小 (2mb)。支持嵌入式和服务器模式以及基于浏览器的控制台应用程序。

{{< card title="Spring Boot With H2 Database" description="In this tutorial, we'll explore using H2 with Spring Boot. Just like other databases, there's full intrinsic support for it in the Spring Boot ecosystem." url="https://www.baeldung.com/spring-boot-h2-database" >}}

### HyperSQL Database

Lightweight 100% Java SQL Database Engine.  
轻量级 100% Java SQL 数据库引擎。

_我选 PostgreSQL_

### MariaDB Driver

MariaDB JDBC and R2DBC driver.  
Mariadb JDBC 和 R2DBC 驱动程序。

_我选 PostgreSQL_

### MS SQL Server Driver

A JDBC and R2DBC driver that provides access to Microsoft SQL Server and Azure SQL Database from any Java application.  
一个 JDBC 和 R2DBC 驱动程序，提供从任何 Java 应用程序访问 Microsoft SQL Server 和 Azure SQL 数据库的权限。

_我选 PostgreSQL_

### MySQL Driver

MySQL JDBC and R2DBC driver.  
MySQL JDBC 和 R2DBC 驱动程序

{{< card "https://dev.mysql.com/doc/mysql-getting-started/en/" >}}
{{< card "https://blog.dramacat.top/mysql/" >}}

### Oracle Driver

A JDBC driver that provides access to Oracle.  
提供对 Oracle 的访问的 JDBC 驱动程序。

{{< card "https://juejin.cn/post/6844903822913978381" >}}
{{< card "https://blog.dramacat.top/oracle/" >}}

### PostgreSQL Driver

A JDBC and R2DBC driver that allows Java programs to connect to a PostgreSQL database using standard, database independent Java code.  
一个 JDBC 和 R2DBC 驱动程序，它允许 Java 程序使用标准的、独立于数据库的 Java 代码连接到 PostgreSQL 数据库。

{{< card "https://www.postgresql.org/docs/current/preface.html" >}}

## NoSQL

### Spring Data Redis (Access+Driver)

Advanced and thread-safe Java Redis client for synchronous, asynchronous, and reactive usage. Supports Cluster, Sentinel, Pipelining, Auto-Reconnect, Codecs and much more.  
用于同步、异步和反应式使用的高级且线程安全的 Java Redis 客户端。支持集群、哨兵、流水线、自动重新连接、编解码器等等。

{{< card "https://redis.io/docs/getting-started/" >}}

### Spring Data Reactive Redis

Access Redis key-value data stores in a reactive fashion with Spring Data Redis.  
使用 Spring Data Redis 以反应方式访问 Redis 键值数据存储。

{{< card "https://spring.io/guides/gs/spring-data-reactive-redis/" >}}

### Spring Data MongoDB

Store data in flexible, JSON-like documents, meaning fields can vary from document to document and data structure can be changed over time.  
将数据存储在灵活的、类似 JSON 的文档中，这意味着字段可以因文档而异，并且数据结构可以随着时间而改变。

{{< card "https://www.mongodb.com/docs/manual/tutorial/getting-started/" >}}

### Spring Data Reactive MongoDB

Provides asynchronous stream processing with non-blocking back pressure for MongoDB.  
为 MongoDB 提供非阻塞背压的异步流处理。

### Spring Data Elasticsearch (Access+Driver)

A distributed, RESTful search and analytics engine with Spring Data Elasticsearch.  
具有弹簧数据弹性搜索的分布式、宁静的搜索和分析引擎。

{{< card "https://www.elastic.co/guide/cn/elasticsearch/guide/current/foreword_id.html" >}}

### Spring Data for Apache Cassandra

A free and open-source, distributed, NoSQL database management system that offers high-scalability and high-performance.  
一个免费且开源的分布式 nosql 数据库管理系统，可提供高可扩展性和高性能。

{{< card "https://cassandra.apache.org/_/quickstart.html" >}}

### Spring Data Reactive for Apache Cassandra

Access Cassandra NoSQL Database in a reactive fashion.  
以反应方式访问 Cassandra NoSQL 数据库。

### Spring for Apache Geode

Apache Geode is a data management platform that helps users build real-time, highly concurrent, highly performant and reliable Spring Boot applications at scale that is compatible with Pivotal Cloud Cache.  
Apache Geode 是一个数据管理平台，可帮助用户大规模构建实时、高并发、高性能和可靠的 Spring Boot 应用程序，并与关键的云缓存兼容。

_我选 Redis_

### Spring Data Couchbase

NoSQL document-oriented database that offers in memory-first architecture, geo-distributed deployments, and workload isolation.  
NoSQL 面向文档的数据库，提供内存优先架构、地理分布式部署和工作负载隔离。

{{< card "https://docs.couchbase.com/server/current/introduction/why-couchbase.html" >}}

### Spring Data Reactive Couchbase

Access Couchbase NoSQL database in a reactive fashion with Spring Data Couchbase.  
使用 Spring Data Couchbase 以反应方式访问 Couchbase NoSQL 数据库。

### Spring Data Neo4j

An open source NoSQL database that stores data structured as graphs consisting of nodes, connected by relationships.  
一个开源的 NoSQL 数据库，将数据存储为由节点组成的图形，并通过关系连接。

{{< card "https://neo4j.com/developer/get-started/" >}}

## Messaging

### Spring Integration

Adds support for Enterprise Integration Patterns. Enables lightweight messaging and supports integration with external systems via declarative adapters.  
添加对企业集成模式的支持。支持轻量级消息传递并支持通过声明性适配器与外部系统集成。

{{< card "https://docs.spring.io/spring-integration/docs/current/reference/html/index-single.html" >}}

_Apache Camel 或许是你更好的选择_

### Spring for RabbitMQ

Gives your applications a common platform to send and receive messages, and your messages a safe place to live until received.  
为您的应用程序提供一个发送和接收消息的通用平台，并为您的消息提供一个安全的地方，直到收到为止。

{{< card "https://www.rabbitmq.com/tutorials/tutorial-one-java.html" >}}

### Spring for Apache Kafka

Publish, subscribe, store, and process streams of records.  
发布、订阅、存储和处理记录流。

{{< card "https://kafka.apache.org/quickstart" >}}

### Spring for Apache Kafka Streams

Building stream processing applications with Apache Kafka Streams.  
使用 Apache Kafka 流构建流处理应用程序。

### Spring for Apache ActiveMQ 5

Spring JMS support with Apache ActiveMQ 'Classic'.  
Spring JMS 支持 Apache ActiveMQ 'Classic'。

_目前没什么优势了_

### Spring for Apache ActiveMQ Artemis

Spring JMS support with Apache ActiveMQ Artemis.  
Spring JMS 支持 Apache ActiveMQ Artemis。

### WebSocket

Build WebSocket applications with SockJS and STOMP.  
使用 SockJS 和 STOMP 构建 Web 套接字应用程序。

{{< card "https://spring.io/guides/gs/messaging-stomp-websocket/" >}}

### RSocket

RSocket.io applications with Spring Messaging and Netty.  
带有 Spring 消息传递和 Netty 的 RSocket.io 应用程序。

{{< card "https://rsocket.io/about/faq" >}}
{{< card "https://spring.io/blog/2020/03/02/getting-started-with-rsocket-spring-boot-server" >}}

### Apache Camel

Apache Camel is an open source integration framework that empowers you to quickly and easily integrate various systems consuming or producing data.  
Apache Camel 是一个开源集成框架，使您能够快速轻松地集成各种消费或生产数据的系统。

{{< card "https://camel.apache.org/manual/getting-started.html" >}}

### Solace PubSub+

Connect to a Solace PubSub+ Advanced Event Broker to publish, subscribe, request/reply and store/replay messages  
连接到 Solace Pub Sub+ 高级事件代理以发布、订阅、请求/回复和存储/重播消息

_目前没有什么案例_

## I/O

### Spring Batch

Batch applications with transactions, retry/skip and chunk based processing.  
具有事务、重试/跳过和基于块的处理的批处理应用程序。

{{< card "https://spring.io/guides/gs/batch-processing/" >}}

### Validation

Bean Validation with Hibernate validator.  
使用休眠验证器进行 Bean 验证。

{{< card "https://spring.io/guides/gs/validating-form-input/" >}}

### Java Mail Sender

Send email using Java Mail and Spring Framework's JavaMailSender.  
使用 Java Mail 和 Spring 框架的 Java Mail Sender 发送电子邮件。

{{< card title="Guide to Spring Email" description="In this tutorial, we'll walk through the steps needed to send emails from both a plain vanilla Spring application as well as a Spring Boot application. For the former, we'll use the JavaMail library, and the latter will use the spring-boot-starter-mail dependency." url="https://www.baeldung.com/spring-email" >}}

### Quartz Scheduler

Schedule jobs using Quartz.  
使用石英安排作业。

{{< card "http://www.quartz-scheduler.org/documentation/2.4.0-SNAPSHOT/quick-start-guide.html" >}}

### Spring cache abstraction

Provides cache-related operations, such as the ability to update the content of the cache, but does not provide the actual data store.  
提供缓存相关的操作，例如更新缓存内容的能力，但不提供实际的数据存储。

{{< card "https://spring.io/guides/gs/caching/" >}}

### Picocli

Build command line applications with picocli.  
使用 Picocli 构建命令行应用程序。

{{< card "https://picocli.info/quick-guide.html" >}}

### Spring Shell

Build command line applications with spring.  
使用 Spring 构建命令行应用程序。

{{< card "https://docs.spring.io/spring-shell/docs/2.1.1/site/reference/htmlsingle/" >}}

## Ops

### Spring Boot Actuator

Supports built in (or custom) endpoints that let you monitor and manage your application - such as application health, metrics, sessions, etc.  
支持内置（或自定义）端点，可让您监控和管理应用程序 - 例如应用程序运行状况、指标、会话等。

{{< card "https://spring.io/guides/gs/actuator-service/" >}}
{{< card "https://docs.spring.io/spring-boot/docs/2.1.2.RELEASE/reference/html/production-ready-endpoints.html" >}}

### Codecentric's Spring Boot Admin (Client)

Required for your application to register with a Codecentric's Spring Boot Admin Server instance.  
您的应用程序需要向 Codecentric 的 Spring Boot Admin Server 实例注册。

{{< card "https://codecentric.github.io/spring-boot-admin/" >}}
{{< card title="A Guide to Spring Boot Admin" url="https://www.baeldung.com/spring-boot-admin" >}}
{{< card "https://github.com/spring-projects/spring-boot/issues/15039" >}}

### Codecentric's Spring Boot Admin (Server)

A community project to manage and monitor your Spring Boot applications. Provides a UI on top of the Spring Boot Actuator endpoints.  
一个社区项目，用于管理和监控您的 Spring Boot 应用程序。在 Spring Boot Actuator 端点之上提供 UI。

{{< card "https://codecentric.github.io/spring-boot-admin/" >}}
{{< card title="A Guide to Spring Boot Admin" url="https://www.baeldung.com/spring-boot-admin" >}}

## Observability

### Datadog

Publish Micrometer metrics to Datadog, a dimensional time-series SaaS with built-in dashboarding and alerting.  
将微米指标发布到 Datadog，这是一种具有内置仪表板和警报的维度时间序列 SaaS。

{{< card title="Getting Started in Datadog" description="The Datadog site navigation varies based on the width of your browser. You can have up to three types of navigation." url="https://docs.datadoghq.com/getting_started/application/" >}}

### Influx

Publish Micrometer metrics to InfluxDB, a dimensional time-series server that support real-time stream processing of data.  
将微米指标发布到 InfluxDB，这是一个支持数据实时流处理的维度时间序列服务器。

{{< card title="Get started with InfluxDB" url="https://docs.influxdata.com/influxdb/v2.4/get-started/" >}}

### Graphite

Publish Micrometer metrics to Graphite, a hierarchical metrics system backed by a fixed-size database.  
将微米度量发布到石墨，这是一个由固定大小数据库支持的分层度量系统。

{{< card "https://docs.graphite.dev/getting-started/getting-started-with-graphite" >}}

### New Relic

Publish Micrometer metrics to New Relic, a SaaS offering with a full UI and a query language called NRQL.  
将千分尺度量发布到 New Relic，这是一种具有完整 UI 和称为 NRQL 的查询语言的 SaaS 产品。

{{< card "https://newrelic.com/resources/white-papers/getting-started-with-new-relic-apm" >}}

### Prometheus

Expose Micrometer metrics in Prometheus format, an in-memory dimensional time series database with a simple built-in UI, a custom query language, and math operations.  
以 Prometheus 格式公开千分尺度量，这是一个内存维度时间序列数据库，具有简单的内置 UI、自定义查询语言和数学运算。

{{< card "https://prometheus.io/docs/prometheus/latest/getting_started/" >}}

### Sleuth

Distributed tracing via logs with Spring Cloud Sleuth.  
使用 Spring Cloud Sleuth 通过日志进行分布式跟踪。

{{< card title="Spring Cloud Sleuth in a Monolith Application" description="In this article, we're introducing Spring Cloud Sleuth – a powerful tool for enhancing logs in any application, but especially in a system built up of multiple services." url="https://www.baeldung.com/spring-cloud-sleuth-single-application" >}}

### Wavefront

Publish Micrometer metrics to Tanzu Observability by Wavefront, a SaaS-based metrics monitoring and analytics platform that lets you visualize, query, and alert over data from across your entire stack.  
通过 Wavefront 将微米指标发布到 Tanzu Observability，这是一个基于 SaaS 的指标监控和分析平台，可让您对整个堆栈中的数据进行可视化、查询和警报。

{{< card "https://bakingclouds.com/getting-started-with-wavefront/" >}}

### Zipkin Client

Distributed tracing with an existing Zipkin installation and Spring Cloud Sleuth Zipkin.  
使用现有的 Zipkin 安装和 Spring Cloud Sleuth Zipkin 进行分布式跟踪。

{{< card "https://zipkin.io/pages/quickstart.html" >}}

## Testing

### Spring REST Docs

Document RESTful services by combining hand-written with Asciidoctor and auto-generated snippets produced with Spring MVC Test.  
通过将手写与 Asciidoctor 和使用 Spring MVC 测试生成的自动生成的片段相结合来记录宁静的服务。

{{< card "https://spring.io/guides/gs/testing-restdocs/" >}}

### Testcontainers

Provide lightweight, throwaway instances of common databases, Selenium web browsers, or anything else that can run in a Docker container.  
提供通用数据库、Selenium WEB 浏览器或任何其他可以在 Docker 容器中运行的轻量级、一次性实例。

{{< card "https://www.testcontainers.org/quickstart/junit_5_quickstart/" >}}

### Contract Verifier

Moves TDD to the level of software architecture by enabling Consumer Driven Contract (CDC) development.  
通过支持消费者驱动的合同 (CDC) 开发，将 TDD 移动到软件架构级别。

{{< card "https://cloud.spring.io/spring-cloud-contract/2.0.x/multi/multi__spring_cloud_contract_verifier_introduction.html" >}}

### Contract Stub Runner

Stub Runner for HTTP/Messaging based communication. Allows creating WireMock stubs from RestDocs tests.  
Stub Runner，用于基于 HTTP/Messaging 的通信。允许从其余文档测试中创建线模拟存根。

{{< card "https://cloud.spring.io/spring-cloud-contract/1.2.x/multi/multi__spring_cloud_contract_stub_runner.html" >}}

### Embedded LDAP Server

Provides a platform neutral way for running a LDAP server in unit tests.  
为在单元测试中运行 LDAP 服务器提供了一种平台中立的方式。

### Embedded MongoDB Database

Provides a platform neutral way for running MongoDB in unit tests.  
为在单元测试中运行 MongoDB 提供了一种平台中立的方式。

{{< card title="Spring Boot Integration Testing with Embedded MongoDB" description="In this tutorial, we'll learn how to use Flapdoodle's embedded MongoDB solution together with Spring Boot to run MongoDB integration tests smoothly." url="https://www.baeldung.com/spring-boot-embedded-mongodb" >}}

## Spring Cloud

### Cloud Bootstrap

Non-specific Spring Cloud features, unrelated to external libraries or integrations (e.g. Bootstrap context and @RefreshScope).

### Function

Promotes the implementation of business logic via functions and supports a uniform programming model across serverless providers, as well as the ability to run standalone (locally or in a PaaS).

### Task

Allows a user to develop and run short lived microservices using Spring Cloud. Run them locally, in the cloud, and on Spring Cloud Data Flow.

## Spring Cloud Tools

### Open Service Broker

Framework for building Spring Boot apps that implement the Open Service Broker API, which can deliver services to applications running within cloud native platforms such as Cloud Foundry, Kubernetes and OpenShift.

## Spring Cloud Config

### Config Client

Client that connects to a Spring Cloud Config Server to fetch the application's configuration.

### Config Server

Central management for configuration via Git, SVN, or HashiCorp Vault.

### Vault Configuration

Provides client-side support for externalized configuration in a distributed system. Using HashiCorp's Vault you have a central place to manage external secret properties for applications across all environments.

### Apache Zookeeper Configuration

Enable and configure common patterns inside your application and build large distributed systems with Apache Zookeeper based components. The provided patterns include Service Discovery and Configuration.

### Consul Configuration

Enable and configure the common patterns inside your application and build large distributed systems with Hashicorp’s Consul. The patterns provided include Service Discovery, Distributed Configuration and Control Bus.

## Spring Cloud Discovery

### Eureka Discovery Client

A REST based service for locating services for the purpose of load balancing and failover of middle-tier servers.

### Eureka Server

spring-cloud-netflix Eureka Server.

### Apache Zookeeper Discovery

Service discovery with Apache Zookeeper.

### Cloud Foundry Discovery

Service discovery with Cloud Foundry.

### Consul Discovery

Service discovery with Hashicorp Consul.

## Spring Cloud Routing

### Gateway

Provides a simple, yet effective way to route to APIs and provide cross cutting concerns to them such as security, monitoring/metrics, and resiliency.

### OpenFeign

Declarative REST Client. OpenFeign creates a dynamic implementation of an interface decorated with JAX-RS or Spring MVC annotations.

### Cloud LoadBalancer

Client-side load-balancing with Spring Cloud LoadBalancer.

## Spring Cloud Circuit Breaker

### Resilience4J

Spring Cloud Circuit breaker with Resilience4j as the underlying implementation.

## Spring Cloud Messaging

### Cloud Bus

Links nodes of a distributed system with a lightweight message broker which can used to broadcast state changes or other management instructions (requires a binder, e.g. Apache Kafka or RabbitMQ).

### Cloud Stream

Framework for building highly scalable event-driven microservices connected with shared messaging systems (requires a binder, e.g. Apache Kafka, RabbitMQ or Solace PubSub+).

## VMware Tanzu Application Service

### Config Client (TAS)

Config client on VMware Tanzu Application Service.  
在 Vmware Tanzu 应用程序服务上配置客户端。

### Service Registry (TAS)

Eureka service discovery client on VMware Tanzu Application Service.  
Vmware Tanzu 应用程序服务上的 Eureka 服务发现客户端。

## Microsoft Azure

### Azure Support

Auto-configuration for Azure Services (Service Bus, Storage, Active Directory, Key Vault, and more).  
Azure 服务（服务总线、存储、活动目录、密钥保管库等）的自动配置。

### Azure Active Directory

Spring Security integration with Azure Active Directory for authentication.  
Spring 安全集成与 Azure 活动目录进行身份验证。

### Azure Cosmos DB

Fully managed NoSQL database service for modern app development, including Spring Data support.  
用于现代应用程序开发的完全托管的 NoSQL 数据库服务，包括 Spring 数据支持。

### Azure Key Vault

All key vault features are supported, e.g. manage application secrets and certificates.  
支持所有密钥保管库功能，例如管理应用程序机密和证书。

### Azure Storage

All Storage features are supported, e.g. blob, fileshare and queue.  
支持所有存储功能，例如 blob、文件共享和队列。

## Google Cloud Platform

### GCP Support

Contains auto-configuration support for every Spring Cloud GCP integration. Most of the auto-configuration code is only enabled if other dependencies are added to the classpath.  
包含对每个 Spring Cloud GCP 集成的自动配置支持。大多数自动配置代码仅在其他依赖项添加到类路径时才启用。

### GCP Messaging

Adds the GCP Support entry and all the required dependencies so that the Google Cloud Pub/Sub integration work out of the box.  
添加 GCP 支持条目和所有必需的依赖项，以便 Google Cloud Pub/Sub 集成开箱即用。

### GCP Storage

Adds the GCP Support entry and all the required dependencies so that the Google Cloud Storage integration work out of the box.  
添加 GCP 支持条目和所有必需的依赖项，以便 Google 云存储集成开箱即用。

## 不在 Spring Initializr 中的其它好用依赖

### Hutool

[Hutool](https://www.hutool.cn/) 是一个小而全的 Java 工具类库，通过静态方法封装，降低相关 API 的学习成本，提高工作效率，使 Java 拥有函数式语言般的优雅，让 Java 语言也可以“甜甜的”。  
Hutool 中的工具方法来自每个用户的精雕细琢，它涵盖了 Java 开发底层代码中的方方面面，它既是大型项目开发中解决小问题的利器，也是小型项目中的效率担当；  
Hutool 是项目中“util”包友好的替代，它节省了开发人员对项目中公用类和公用工具方法的封装时间，使开发专注于业务，同时可以最大限度的避免封装不完善带来的 bug。

{{< card "https://www.hutool.cn/docs/#/" >}}

### MyBatis-Plus

[MyBatis-Plus](https://baomidou.com/)（简称 MP）是一个 MyBatis 的增强工具，在 MyBatis 的基础上只做增强不做改变，为简化开发、提高效率而生。

{{< card "https://baomidou.com/" >}}
