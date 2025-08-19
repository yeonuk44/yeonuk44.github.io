---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_C_Context
title: C 컨텍스트(Context)에 대하여
# title: About C Context
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Development
# multiple tag entries are possible
tags: [development]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2025-08-20 09:00:00 +0900
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

## MyBatis: 개발자를 위한 유연한 SQL 매퍼 프레임워크에 대하여 알아본 글입니다.

안녕하세요!

Java 애플리케이션 개발에서 데이터베이스와의 상호작용은 필수적인 작업입니다.

MyBatis는 이 과정을 간소화하고 효율적으로 관리하기 위해 설계된 **SQL 매퍼 프레임워크**로, 데이터베이스 쿼리 실행과 객체 매핑의 유연성을 제공합니다.

이번 글에서는 MyBatis의 특징, 장단점, 그리고 기본 사용법에 대해 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### **MyBatis란?**

MyBatis는 **Java** 및 **SQL** 기반의 퍼시스턴스 프레임워크로, 개발자가 SQL, 저장 프로시저, 그리고 고유한 매핑 규칙을 사용하여 데이터베이스와 상호작용할 수 있도록 지원합니다.

특히 MyBatis는 ORM(Object-Relational Mapping) 도구인 Hibernate와는 다르게, SQL을 직접 작성하여 세밀한 데이터베이스 조작이 가능합니다.

### **MyBatis의 주요 특징**

1. **SQL 중심의 데이터 매핑**

   - 개발자가 SQL을 직접 작성하여 데이터베이스 작업을 제어합니다.
   - XML 또는 어노테이션을 사용해 SQL 문장을 정의할 수 있습니다.

2. **유연한 매핑**

   - 데이터베이스의 테이블과 Java 객체 간의 매핑을 간단히 설정할 수 있습니다.
   - 복잡한 관계형 데이터베이스 구조를 손쉽게 객체화합니다.

3. **강력한 커스터마이징**

   - MyBatis는 SQL을 직접 제어하므로 복잡한 쿼리를 처리하거나 고성능 쿼리를 최적화할 수 있습니다.
   - 다양한 캐싱 전략과 플러그인을 제공하여 성능을 향상시킬 수 있습니다.

4. **간단한 설정**
   - MyBatis는 설정 파일(XML)과 최소한의 Java 코드만으로 작동합니다.
   - 별도의 스키마 생성이나 ORM에 의존하지 않습니다.

### **MyBatis의 장단점**

#### **장점**

- **SQL 제어**: 개발자가 SQL 문을 직접 작성하여 높은 수준의 데이터베이스 제어 가능.
- **유연성**: ORM 도구가 처리하기 어려운 복잡한 쿼리와 관계를 쉽게 다룰 수 있음.
- **빠른 학습 곡선**: SQL에 익숙한 개발자는 빠르게 MyBatis를 습득할 수 있음.
- **XML 지원**: XML 파일을 통해 명확하고 선언적인 방식으로 매핑 설정 가능.

#### **단점**

- **SQL 작성 부담**: SQL을 직접 작성해야 하므로, 코드 양이 많아질 수 있음.
- **유지보수 어려움**: 쿼리가 많아질수록 유지보수가 복잡해질 수 있음.
- **비표준화**: 특정 데이터베이스에 의존적인 SQL 문장을 작성할 가능성이 높음.

### **MyBatis 기본 사용법**

#### **1. 설정 파일 구성**

MyBatis는 `mybatis-config.xml` 파일을 통해 설정됩니다.

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

#### **2. 매핑 파일 구성**

`mapper.xml` 파일에서 SQL 문과 객체 매핑을 정의합니다.

```xml
<mapper namespace="com.example.mapper.UserMapper">
    <select id="getUserById" parameterType="int" resultType="com.example.model.User">
        SELECT * FROM users WHERE id = #{id}
    </select>
</mapper>
```

#### **3. DAO 인터페이스 작성**

매퍼 파일과 연결되는 인터페이스를 작성합니다.

```java
package com.example.mapper;

import com.example.model.User;

public interface UserMapper {
    User getUserById(int id);
}
```

#### **4. MyBatis를 사용한 데이터 조회**

Java 코드에서 MyBatis 세션을 통해 데이터베이스 작업을 수행합니다.

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

### **MyBatis를 사용할 때 고려해야 할 점**

1. **SQL 재사용**

   - XML 매퍼에서 `<sql>` 태그를 활용해 공통 SQL 구문을 재사용할 수 있습니다.

2. **트랜잭션 관리**

   - MyBatis 자체적으로 트랜잭션 관리를 제공하지만, Spring과 통합하여 관리하는 것이 더 일반적입니다.

3. **캐싱 활용**
   - MyBatis는 1차, 2차 캐싱을 제공하므로, 성능 최적화를 위해 적절히 사용해야 합니다.

---

### **결론**

MyBatis는 SQL 중심의 데이터 매핑을 선호하는 개발자들에게 적합한 프레임워크로, 간단한 설정과 강력한 커스터마이징 기능을 제공합니다.

SQL을 직접 작성함으로써 데이터베이스 작업을 더 세밀히 제어할 수 있으며, 복잡한 데이터 구조를 다룰 때 매우 유용합니다.

하지만, SQL 관리가 어려울 수 있으므로 코드 품질과 유지보수를 고려한 설계가 필요합니다.

MyBatis의 장점을 극대화하려면 Spring과 통합하여 사용하거나 적절한 매핑 전략을 수립하는 것이 좋습니다.

MyBatis를 활용해 데이터베이스와의 상호작용을 효과적으로 관리해 보세요! 🚀
