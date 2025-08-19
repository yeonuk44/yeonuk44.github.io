---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_MyBatis
title: About MyBatis
# title: About MyBatis
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: SQL
# multiple tag entries are possible
tags: [sql]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2025-08-14 09:00:00 +0900
# seo
# if not specified, date will be used.
#meta_modify_date: 2021-08-10 11:32:53 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# please use the "image_viewer_on" below to enable image viewer for individual pages or posts (_posts/ or [language]/_posts folders).
# image viewer can be enabled or disabled for all posts using the "image_viewer_posts: true" setting in _data/conf/main.yml.
#image_viewer_on: true
# please use the "image_lazy_loader_on" below to enable image lazy loader for individual pages or posts (_posts/ or [language]/_posts folders).
# image lazy loader can be enabled or disabled for all posts using the "image_lazy_loader_posts: true" setting in _data/conf/main.yml.
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false
---

<!-- outline-start -->

## MyBatis: A flexible SQL mapper framework for developers.

Hello!

In Java application development, interaction with databases is an essential task.

MyBatis is a **SQL mapper framework** designed to simplify and efficiently manage this process, providing flexibility in database query execution and object mapping.

In this article, we will learn about the features, strengths and weaknesses, and basic usage of MyBatis.

{:data-align="center"}

<!-- outline-end -->

### **MyBatis란?**?

MyBatis is a **Java** and **SQL**-based persistence framework that enables developers to interact with databases using SQL, stored procedures, and unique mapping rules.

In particular, MyBatis, unlike Hibernate, an object-relational mapping (ORM) tool, allows for detailed database manipulation by writing SQL by itself.

### **Key features of MyBatis**

1. **SQL-centric data mapping**

   - Developers create SQL themselves to control database operations.
   - You can define SQL statements using XML or annotations.

2. **Flexible mapping**

   - You can easily set up a mapping between tables in the database and Java objects.
   - Easily objectify complex relational database structures.

3. **Strong customization**

   - MyBatis directly controls SQL, allowing you to handle complex queries or optimize high-performance queries.
   - Provides a variety of caching strategies and plug-ins to improve performance.

4. **Simple settings**
   - MyBatis works with only a configuration file (XML) and minimal Java code.
   - It does not rely on separate schema creation or ORM.

### **The pros and cons of MyBatis**

#### **Advantages**

- **SQL control**: Developers can create SQL statements themselves to control the database at a high level.
- **Flexibility**: Easy to handle complex queries and relationships that ORM tools can't handle.
- **Quick learning curve**: Developers familiar with SQL are quick to

## MyBatis: A flexible SQL mapper framework for developers.

Hello!

In Java application development, interaction with databases is an essential task.

MyBatis is a **SQL mapper framework** designed to simplify and efficiently manage this process, providing flexibility in database query execution and object mapping.

In this article, we will learn about the features, strengths and weaknesses, and basic usage of MyBatis.

{:data-align="center"}

<!-- outline-end -->

### **MyBatis란?**?

MyBatis is a **Java** and **SQL**-based persistence framework that enables developers to interact with databases using SQL, stored procedures, and unique mapping rules.

In particular, MyBatis, unlike Hibernate, an object-relational mapping (ORM) tool, allows for detailed database manipulation by writing SQL by itself.

### **Key features of MyBatis**

1. **SQL-centric data mapping**

   - Developers create SQL themselves to control database operations.
   - You can define SQL statements using XML or annotations.

2. **Flexible mapping**

   - You can easily set up a mapping between tables in the database and Java objects.
   - Easily objectify complex relational database structures.

3. **Strong customization**

   - MyBatis directly controls SQL, allowing you to handle complex queries or optimize high-performance queries.
   - Provides a variety of caching strategies and plug-ins to improve performance.

4. **Simple settings**
   - MyBatis works with only a configuration file (XML) and minimal Java code.
   - It does not rely on separate schema creation or ORM.

### **The pros and cons of MyBatis**

#### **Advantages**

- **SQL control**: Developers can create SQL statements themselves to control the database at a high level.
- **Flexibility**: Easy to handle complex queries and relationships that ORM tools can't handle.
- **Quick learning curve**: Developers familiar with SQL can quickly acquire MyBatis.
- **XML support**: XML files allow mapping to be established in a clear and declarative manner.

#### **Disadvantages**

- **SQL writing burden**: SQL needs to be written by yourself, so the amount of code can be high.
- **Maintenance difficulties**: More queries can complicate maintenance.
- **Non-standardized**: likely to write SQL statements that are dependent on a particular database.

### **MyBatis basic usage**

#### **1. Configuring Settings File**

MyBatis is set through the 'mybatis-config.xml' file.

```xml
<configuration>
    <environments default="development">
        <environment id="development">
            <transactionManager type="JDBC" />
            <dataSource type="POOLED">
                <property name="driver" value="com.mysql.cj.jdbc.Driver" />
                <property name="url" value="jdbc:mysql://localhost:3306/mydb" />
                <property name="username" value="root" />
                <property name="password" value="password" />
            </dataSource>
        </environment>
    </environments>
</configuration>
```

#### **2. Configure mapping files**

Define SQL statements and object mapping in the 'mapper.xml' file.

```xml
<mapper namespace="com.example.mapper.UserMapper">
    <select id="getUserById" parameterType="int" resultType="com.example.model.User">
        SELECT * FROM users WHERE id = #{id}
    </select>
</mapper>
```

#### **3. Create a DAO interface**

Create an interface that associates with the mapper file.

```java
package com.example.mapper;

import com.example.model.User;

public interface UserMapper {
    User getUserById(int id);
}
```

#### **4. Data inquiry using MyBatis**

Perform database operations through MyBatis sessions in Java code.

```java
import org.apache.ibatis.session.SqlSession;
import org.apache.ibatis.session.SqlSessionFactory;

public class MyBatisExample {
    public static void main(String[] args) {
        SqlSessionFactory sqlSessionFactory = MyBatisUtil.getSqlSessionFactory();
        try (SqlSession session = sqlSessionFactory.openSession()) {
            UserMapper userMapper = session.getMapper(UserMapper.class);
            User user = userMapper.getUserById(1);
            System.out.println("User Name: " + user.getName());
        }
    }
}
```

---

### **What to consider when using MyBatis**

1. **Reuse SQL**

   - You can reuse common SQL syntax using the '<sql>' tag in XML mapper.

2. **Transaction management**

   - MyBatis provides transaction management on its own, but it is more common to integrate with Spring.

3. **Using Caching**
   - Because MyBatis provides primary and secondary caching, it should be used appropriately for performance optimization.

---

### **Conclusion**

MyBatis is a framework suitable for developers who prefer SQL-centric data mapping, providing simple setup and powerful customization.

By writing SQL directly, you can gain greater control over database operations, which are very useful when dealing with complex data structures.

However, SQL management can be challenging and requires a design that takes code quality and maintenance into account.

To maximize the benefits of MyBatis, it is recommended to integrate with Spring or to establish the appropriate mapping strategy.

Use MyBatis to effectively manage your database interactions! 🚀
