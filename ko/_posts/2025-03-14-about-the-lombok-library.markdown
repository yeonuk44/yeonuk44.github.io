---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-about-the-lombok-library
title: Lombok 라이브러리에 대하여 (with. Java)
# title: About the Lombok Library (with. Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2025-03-14 09:00:00 +0900
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

# **Lombok: 자바 개발자를 위한 필수 라이브러리**를 알아본 글입니다.

Java 개발을 하다 보면 반복적인 코드 작성이 피할 수 없는 경우가 많습니다.

예를 들어, 데이터 클래스를 작성할 때 `getter`, `setter`, `toString`, `equals`, `hashCode` 메서드를 매번 생성해야 하는 불편함이 있습니다.

이와 같은 반복 작업을 줄이고, 코드의 가독성을 높이기 위해 등장한 라이브러리가 바로 **Lombok**입니다.

{:data-align="center"}

<!-- outline-end -->

## **Lombok란 무엇인가?**

**Lombok**은 자바 애플리케이션 개발에서 반복적으로 작성되는 코드를 자동으로 생성해주는 라이브러리입니다.

컴파일 시점에 애노테이션을 분석해 필요한 코드를 삽입하여 개발자의 작업을 줄이고, 더 간결하고 깔끔한 코드를 작성할 수 있도록 도와줍니다.

Lombok은 특히 **DTO (Data Transfer Object)**와 같은 데이터 중심의 클래스를 작성할 때 유용합니다.

IDE에서 직접 코드 생성 없이 애노테이션만으로 원하는 메서드와 필드를 제공받을 수 있습니다.

## **Lombok의 주요 애노테이션**

### 1. **@Getter / @Setter**

- **설명**: 클래스의 필드에 대해 `getter`와 `setter` 메서드를 자동으로 생성.
- **예제**:

  ```java
  import lombok.Getter;
  import lombok.Setter;

  @Getter
  @Setter
  public class User {
      private String name;
      private int age;
  }
  ```

- **결과**: 위 코드로 인해 `getName()`, `setName(String name)`, `getAge()`, `setAge(int age)` 메서드가 자동 생성됩니다.

### 2. **@ToString**

- **설명**: 클래스의 `toString` 메서드를 자동으로 생성.
- **예제**:

  ```java
  import lombok.ToString;

  @ToString
  public class User {
      private String name;
      private int age;
  }
  ```

- **결과**: 객체를 출력하면 `"User(name=John, age=25)"`과 같은 포맷으로 출력됩니다.

### 3. **@EqualsAndHashCode**

- **설명**: `equals`와 `hashCode` 메서드를 자동으로 생성.
- **예제**:

  ```java
  import lombok.EqualsAndHashCode;

  @EqualsAndHashCode
  public class User {
      private String name;
      private int age;
  }
  ```

- **결과**: 객체의 내용에 따라 `equals`와 `hashCode` 메서드가 동작합니다.

### 4. **@NoArgsConstructor / @AllArgsConstructor / @RequiredArgsConstructor**

- **설명**: 다양한 형태의 생성자를 자동으로 생성.
  - **`@NoArgsConstructor`**: 파라미터 없는 기본 생성자.
  - **`@AllArgsConstructor`**: 모든 필드를 매개변수로 받는 생성자.
  - **`@RequiredArgsConstructor`**: `final` 필드 또는 `@NonNull` 필드만 매개변수로 받는 생성자.
- **예제**:

  ```java
  import lombok.AllArgsConstructor;
  import lombok.NoArgsConstructor;

  @NoArgsConstructor
  @AllArgsConstructor
  public class User {
      private String name;
      private int age;
  }
  ```

- **결과**: 두 가지 형태의 생성자가 자동으로 제공됩니다.

### 5. **@Data**

- **설명**: `@Getter`, `@Setter`, `@ToString`, `@EqualsAndHashCode`, `@RequiredArgsConstructor`를 한 번에 제공.
- **예제**:

  ```java
  import lombok.Data;

  @Data
  public class User {
      private String name;
      private int age;
  }
  ```

- **결과**: 데이터 중심 클래스에 필요한 모든 메서드를 자동 생성.

### 6. **@Builder**

- **설명**: 빌더 패턴을 쉽게 구현하도록 지원.
- **예제**:

  ```java
  import lombok.Builder;

  @Builder
  public class User {
      private String name;
      private int age;
  }
  ```

- **사용**:
  ```java
  User user = User.builder()
                  .name("John")
                  .age(25)
                  .build();
  ```

### 7. **@Slf4j**

- **설명**: 클래스에 `Logger` 객체를 자동으로 생성.
- **예제**:

  ```java
  import lombok.extern.slf4j.Slf4j;

  @Slf4j
  public class Example {
      public void logExample() {
          log.info("This is a log message!");
      }
  }
  ```

## **Lombok의 장점**

1. **코드 간소화**  
   반복적인 코드를 줄이고, 간결하고 읽기 쉬운 코드를 작성할 수 있습니다.

2. **생산성 향상**  
   getter, setter, toString 등의 메서드 작성 시간을 절약할 수 있습니다.

3. **가독성 향상**  
   비즈니스 로직에만 집중할 수 있도록 코드의 구조를 단순화합니다.

## **Lombok의 단점**

1. **IDE 의존성**  
   Lombok은 IDE의 플러그인을 설치해야 제대로 동작합니다. 플러그인 없이 코드를 보면 이해하기 어렵습니다.

2. **런타임 디버깅**  
   컴파일 타임에 코드를 생성하기 때문에 디버깅 시 실제 생성된 코드를 확인하기 어려운 경우가 있습니다.

3. **호환성 문제**  
   특정 환경(예: 일부 빌드 도구나 다른 라이브러리)에서 호환성 문제가 발생할 수 있습니다.

## **결론**

Lombok은 Java 개발을 더 빠르고 효율적으로 만드는 강력한 도구입니다.

반복적인 코드를 제거하고 생산성을 높이며, 간결하고 가독성 좋은 코드를 작성할 수 있도록 도와줍니다.

그러나 Lombok 사용 시 의존성과 디버깅 이슈를 염두에 두어야 합니다.

Lombok을 적절히 활용하여 프로젝트의 품질과 개발 속도를 모두 높여보세요! 🚀
