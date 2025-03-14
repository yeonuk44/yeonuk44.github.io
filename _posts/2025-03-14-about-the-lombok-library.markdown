---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id-about-the-lombok-library
title: About the Lombok Library (with. Java)
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

# \*\*Lombok: essential live for Java developers

# **Lombok: This article examines the required library** for Java developers.

When developing Java, repetitive code writing is often unavoidable.

For example, when creating a data class, it is inconvenient to generate 'getter', 'setter', 'toString', 'equals', and 'hashCode' methods each time.

**Lombok** is the library that emerged to reduce iterations like this and increase readability of code.

{:data-align="center"}

<!-- outline-end -->

## **What is Lombok?**?

**Lombok** is a library that automatically generates code that is repeatedly written by Java application development.

Annotation is analyzed at the time of compilation to insert the necessary code to reduce developer work and help write simpler and cleaner code.

Lombok is particularly useful when creating data-driven classes such as **DTO (Data Transfer Object)**.

You can get the method and field you want with just an annotation without generating code directly from IDE.

## **Lombok's main anote**

### 1. **@Getter / @Setter**

- **Description**: Automatically generate 'getter' and 'setter' methods for fields in the class.
- **Example**:

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

- **Result**: The above code automatically generates methods 'getName(), 'setName(String name), 'getAge()' and 'setAge(intage)'.

### 2. **@ToString**

- **Description**: Automatically creates the 'toString' method of the class.
- **Example**:

  ```java
  import lombok.ToString;

  @ToString
  public class User {
      private String name;
      private int age;
  }
  ```

- **Result**: When an object is printed, it is printed in the same format as 'User(name=John, age=25)"

### 3. **@EqualsAndHashCode**

- **Description**: Automatically create 'equals' and 'hashCode' methods.
- **Example**:

  ```java
  import lombok.EqualsAndHashCode;

  @EqualsAndHashCode
  public class User {
      private String name;
      private int age;
  }
  ```

- **Results**: The 'equals' and 'hashCode' methods operate depending on the contents of the object.

### 4. **@NoArgsConstructor / @AllArgsConstructor / @RequiredArgsConstructor**

- **Description**: Automatically create various types of generators.
  - **`@NoArgsConstructor`**: Default generator with no parameters.
  - **`@AllArgsConstructor`**: A constructor that receives all fields as parameters.
  - **`@RequiredArgsConstructor'**: A constructor that receives only the 'final' or '@NonNull' fields as parameters.
- **Example**:

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

- **Results**: Two types of generators are automatically provided.

### 5. **@Data**

- **설명**: `@Getter`, `@Setter`, `@ToString`, `@EqualsAndHashCode`, `@RequiredArgsConstructor`를 한 번에 제공.
- **Example**:

  ```java
  import lombok.Data;

  @Data
  public class User {
      private String name;
      private int age;
  }
  ```

- **Results**: Automatically generate all the methods required for a data-driven class.

### 6. **@Builder**

- **Description**: Help facilitate the implementation of builder patterns.
- **Example**:

  ```java
  import lombok.Builder;

  @Builder
  public class User {
      private String name;
      private int age;
  }
  ```

- **Use**:
  ```java
  User user = User.builder()
                  .name("John")
                  .age(25)
                  .build();
  ```

### 7. **@Slf4j**

- **Description**: Automatically create 'Logger' object in class.
- **Example**:

  ```java
  import lombok.extern.slf4j.Slf4j;

  @Slf4j
  public class Example {
      public void logExample() {
          log.info("This is a log message!");
      }
  }
  ```

## **Advantages of Lombok**

1. **Simplify code**  
   Reduce repetitive code and write concise and easy-to-read code.

2. **Improves productivity**  
   You can save time writing methods such as getter, setter, to String, and so on.

3. **Advanced readability**  
   Simplifies the structure of the code so that you can focus solely on business logic.

## **Lombok's shortcomings**

1. **IDE Dependency**  
   Lombok needs to install the plug-in of IDE to work properly. It's hard to understand when you look at the code without the plug-in.

2. **Running Debugging**  
   Because code is generated at compilation time, it is sometimes difficult to verify the actual generated code when debugging.

3. **Compatibility issues**  
   Compatibility issues may occur in certain environments (for example, some build tools or other libraries).

## **Conclusion**

Lombok is a powerful tool that makes Java development faster and more efficient.

It helps you remove repetitive codes, increase productivity, and write concise and readable codes.

However, dependency and debugging issues must be kept in mind when using Lombok.

Take advantage of Lombok to speed up both quality and development of your project! 🚀
