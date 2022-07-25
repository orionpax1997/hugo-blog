---
title: "通过 Spring Initializr 了解常用后端框架"
date: 2021-02-14T16:45:54+08:00
categories: ["Development"]
tags: ["Backend Framework"]
featuredImage: "https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/Development/spring-initializr-banner.5jcrfnfqm400.webp"
---

## 简介

> [Spring Initializr](https://start.spring.io/) 从本质上来说就是一个 Web 应用程序，它能为你生成 Spring Boot 项目结构。虽然不能生成应用程序代码，但它能为你提供一个基本的项目结构，以及一个用于构建代码的 Maven 或 Gradle 构建说明文件。你只需要写应用程序的代码就好了。

{{< card "https://start.spring.io/" >}}
{{< card url="https://spring.io/guides" title="Spring Guides" description="Whatever you're building, these guides are designed to get you productive as quickly as possible – using the latest Spring project releases and techniques as recommended by the Spring team.">}}
{{< card "https://spring.io/projects/spring-boot" >}}
{{< card "https://www.springcloud.cc/spring-boot.html" >}}
{{< card "https://github.com/Humble-Xiang/learn-spring-initializr-dependencies" >}}

## DEVELOPER TOOLS

### Lombok

Java annotation library which helps to reduce boilerplate code.

```xml
<dependency>
   <groupId>org.projectlombok</groupId>
   <artifactId>lombok</artifactId>
   <optional>true</optional>
</dependency>
```

```xml
<plugin>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-maven-plugin</artifactId>
   <configuration>
      <excludes>
         <exclude>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
         </exclude>
      </excludes>
   </configuration>
</plugin>
```

{{< card "https://humble-blog.vercel.app/lombok/" >}}
{{< card "https://github.com/Humble-Xiang/learn-spring-initializr-dependencies/tree/main/lombok" >}}

### Spring Configuration Processor

Generate metadata for developers to offer contextual help and "code completion" when working with custom configuration keys (ex.application.properties/.yml files).

给自定义的配置类生成元数据信息，可以在你编写配置文件时，对自定义的配置提供提示。

```xml
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-configuration-processor</artifactId>
   <optional>true</optional>
</dependency>
<!-- 由於spring-boot-configuration-processor只是用來產生metadata檔，程式執行時用不到，所以從spring-boot-maven-plugin的中排除，這樣建構時才不會被打包 -->
<plugin>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-maven-plugin</artifactId>
	<configuration>
		<excludes>
			<exclude>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-configuration-processor</artifactId>
			</exclude>
		</excludes>
	</configuration>
</plugin>
```

```java
@Getter
@Setter
@EnableConfigurationProperties(value = CustomProperties.class)
@ConfigurationProperties(value = "custom")
public class CustomProperties {

    /**
     * 项目描述
     */
    private String msg;

}
```

![Spring-Configuration-Processor](https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/Development/Spring-Configuration-Processor.3xv8uc74vjw0.webp)

{{< card "https://docs.spring.io/spring-boot/docs/current/reference/html/configuration-metadata.html#configuration-metadata.annotation-processor" >}}
{{< card "https://matthung0807.blogspot.com/2020/09/spring-boot-configuration-processor.html" >}}
{{< card "https://www.freesion.com/article/8342995481/" >}}
{{< card "https://github.com/Humble-Xiang/learn-spring-initializr-dependencies/tree/main/spring-configuration-processor" >}}

## WEB

### Spring Web

Build web, including RESTful, applications using Spring MVC. Uses Apache Tomcat as the default embedded container.

使用 Spring MVC 构建 Web（包括 RESTful）应用程序。 使用 Apache Tomcat 作为默认的嵌入式容器。

```xml
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

{{< card "https://spring.io/guides/gs/rest-service/" >}}
{{< card "https://spring.io/guides/gs/consuming-rest/" >}}

### Spring Reactive Web

Build reactive web applications with Spring WebFlux and Netty.

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-webflux</artifactId>
</dependency>
<dependency>
    <groupId>io.projectreactor</groupId>
    <artifactId>reactor-test</artifactId>
    <scope>test</scope>
</dependency>
```

{{< card "https://spring.io/guides/gs/reactive-rest-service/" >}}

## SQL

### Spring Data R2DBC

Provides Reactive Relational Database Connectivity to persist data in SQL stores using Spring Data in reactive applications.

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-r2dbc</artifactId>
</dependency>
<dependency>
    <groupId>io.projectreactor</groupId>
    <artifactId>reactor-test</artifactId>
    <scope>test</scope>
</dependency>
```

{{< card "https://spring.io/guides/gs/accessing-data-r2dbc/" >}}

### MyBatis Framework

Persistence framework with support for custom SQL, stored procedures and advanced mappings. MyBatis couples objects with stored procedures or SQL statements using a XML descriptor or annotations.

使用 MyBatis 的持久化支持。

```xml
<dependency>
   <groupId>org.mybatis.spring.boot</groupId>
   <artifactId>mybatis-spring-boot-starter</artifactId>
   <version>2.2.0</version>
</dependency>
```

```java
@SpringBootApplication
@MapperScan("top.orionpax.learnspringboot.**.mapper")
public class SpringBootApplication {
...
```

{{< card "https://mybatis.org/mybatis-3/zh/index.html" >}}
{{< card "https://humble-blog.vercel.app/mybatis/" >}}

### MySQL Driver

MySQL JDBC and R2DBC driver.

MySQL JDBC 和 R2DBC 驱动程序

```xml
<dependency>
   <groupId>mysql</groupId>
   <artifactId>mysql-connector-java</artifactId>
   <scope>runtime</scope>
</dependency>
```

```yaml
spring:
  datasource:
    url: jdbc:mysql://ip:port/database
    username: username
    password: password
```

## OPS

### Spring Boot Actuator

Supports built in (or custom) endpoints that let you monitor and manage your application - such as application health, metrics, sessions, etc.

```xml
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```

{{< card "https://spring.io/guides/gs/actuator-service/" >}}
{{< card "https://docs.spring.io/spring-boot/docs/2.1.2.RELEASE/reference/html/production-ready-endpoints.html" >}}

### Codecentric's Spring Boot Admin (Client)

Required for your application to register with a Codecentric's Spring Boot Admin Server instance.

```xml
<dependency>
  <groupId>de.codecentric</groupId>
  <artifactId>spring-boot-admin-starter-client</artifactId>
</dependency>
```

```yaml
spring:
  boot:
    admin:
      client:
        url: admin-server-url
```

{{< card "https://codecentric.github.io/spring-boot-admin/" >}}
{{< card "https://github.com/Humble-Xiang/learn-spring-initializr-dependencies/tree/main/spring-boot-admin-client" >}}

### Codecentric's Spring Boot Admin (Server)

A community project to manage and monitor your Spring Boot applications. Provides a UI on top of the Spring Boot Actuator endpoints.

```xml
<dependency>
  <groupId>de.codecentric</groupId>
  <artifactId>spring-boot-admin-starter-server</artifactId>
</dependency>
```

{{< card "https://codecentric.github.io/spring-boot-admin/" >}}
{{< card "https://github.com/Humble-Xiang/learn-spring-initializr-dependencies/tree/main/spring-boot-admin-server" >}}

## 不在 Spring Initializr 中的其它好用依赖

### Hutool

[Hutool](https://www.hutool.cn/) 是一个小而全的 Java 工具类库，通过静态方法封装，降低相关 API 的学习成本，提高工作效率，使 Java 拥有函数式语言般的优雅，让 Java 语言也可以“甜甜的”。

Hutool 中的工具方法来自每个用户的精雕细琢，它涵盖了 Java 开发底层代码中的方方面面，它既是大型项目开发中解决小问题的利器，也是小型项目中的效率担当；

Hutool 是项目中“util”包友好的替代，它节省了开发人员对项目中公用类和公用工具方法的封装时间，使开发专注于业务，同时可以最大限度的避免封装不完善带来的 bug。

```xml
<dependency>
   <groupId>cn.hutool</groupId>
   <artifactId>hutool-all</artifactId>
   <version>${cn.hutool.version}</version>
</dependency>
```

{{< card "https://www.hutool.cn/docs/#/" >}}

### MyBatis-Plus

[MyBatis-Plus](https://baomidou.com/)（简称 MP）是一个 MyBatis 的增强工具，在 MyBatis 的基础上只做增强不做改变，为简化开发、提高效率而生。

```xml
<dependency>
   <groupId>com.baomidou</groupId>
   <artifactId>mybatis-plus-boot-starter</artifactId>
   <version>${mybatis-plus.version}</version>
</dependency>
<dependency>
   <groupId>com.baomidou</groupId>
   <artifactId>mybatis-plus-generator</artifactId>
   <version>${mybatis-plus-generator.version}</version>
</dependency>
<dependency>
	 <groupId>org.apache.velocity</groupId>
	 <artifactId>velocity-engine-core</artifactId>
	 <version>${velocity.version}</version>
</dependency>
```

```java
package top.orionpax.learnspringboot.generator;

import com.baomidou.mybatisplus.core.exceptions.MybatisPlusException;
import com.baomidou.mybatisplus.generator.FastAutoGenerator;
import com.baomidou.mybatisplus.generator.config.DataSourceConfig;
import com.baomidou.mybatisplus.generator.config.OutputFile;

import java.util.Arrays;
import java.util.Collections;
import java.util.Scanner;

/**
 * MyBatis Plus 逆向生成工具类
 *
 * @author pax
 * @since 2021-09-29
 */
public class MyBatisPlusCodeGenerator {

    /** 数据源配置 */
    private static final DataSourceConfig.Builder DATA_SOURCE_CONFIG = new DataSourceConfig.Builder("jdbc:mysql://host:port/database", "username", "password");
    /** 根路径配置 */
    private static final String ROOT_PATH = "ROOT_PATH";
    /** 父包名配置 */
    private static final String PARENT_PACKAGE_NAME = "PARENT_PACKAGE_NAME";
    /** 过滤表前缀配置 */
    private static final String[] TABLE_PREFIX_LIST = {"T_"};

    /**
     * 执行 run
     */
    public static void main(String[] args) {
        String author = scanner("作者");
        String moduleName = scanner("模块名");
        String tableNames = scanner("表名");
        FastAutoGenerator.create(DATA_SOURCE_CONFIG)
                // 全局配置
                .globalConfig(builder -> builder
                        // 设置输出目录
                        .outputDir(ROOT_PATH + "java")
                        // 设置作者
                        .author(author)
                )
                // 包配置
                .packageConfig((scanner, builder) -> builder
                        // 设置父包名
                        .parent(PARENT_PACKAGE_NAME)
                        // 设置mapperXml生成路径
                        .pathInfo(Collections.singletonMap(OutputFile.mapperXml, ROOT_PATH + "resources/mapper/" + moduleName))
                        // 设置模块名
                        .moduleName(moduleName)
                )
                // 策略配置
                .strategyConfig(builder -> builder
                        // 设置表名，多个英文逗号分隔
                        .addInclude(Arrays.asList(tableNames.split(",")))
                        // 设置过滤表前缀
                        .addTablePrefix(TABLE_PREFIX_LIST)
                        // 设置开启 lombok 模型
                        .entityBuilder().enableLombok()
                        // 设置开启 启用 BaseResultMap 生成、启用 BaseColumnList 生成
                        .mapperBuilder().enableBaseResultMap().enableBaseColumnList()
                        // 设置开启生成 @RestController 控制器
                        .controllerBuilder().enableRestStyle()
                )
                .execute();
    }

    /**
     * 读取控制台内容
     */
    public static String scanner(String tip) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("请输入" + tip + "：");
        if (scanner.hasNext()) {
            return scanner.next();
        }
        throw new MybatisPlusException("请输入正确的" + tip + "！");
    }
}
```

{{< card "https://baomidou.com/" >}}
