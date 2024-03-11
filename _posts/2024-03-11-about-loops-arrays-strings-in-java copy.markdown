---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Loops_Arrays_Strings_In_Java
title: About loops, arrays, and strings (with.Java)
# title: About loops, arrays, and strings (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-03-11 09:00:00 +0900
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

## Java에 타입, 변수, 연산자에 대하여 알아본 글입니다.

이번 글은 정보처리기사를 준비하며 Java 프로그래밍에서 기본이 되는 데이터 타입, 변수, 그리고 연산자에 대해 알아볼 예정입니다.

{:data-align="center"}

<!-- outline-end -->

### 데이터 타입 (Data Types)

크게 기본 데이터 타입(primitive data types)과 참조 데이터 타입(reference data types)으로 나뉩니다.

**기본 데이터 타입**

- 정수형: byte, short, int, long
- 실수형: float, double
- 문자형: char
- 논리형: boolean

**참조 데이터 타입**

- 클래스(Class)
- 인터페이스(Interface)
- 배열(Array)

### 변수 (Variables)

변수는 데이터를 저장하는 메모리 공간을 나타냅니다.

Java에서는 변수를 선언할 때 해당 변수의 데이터 타입을 명시해야 합니다.

변수의 데이터 타입은 변수가 저장할 수 있는 데이터의 종류와 크기를 결정합니다.

예를 들어, 정수를 저장하려면 'int' 데이터 타입을 사용하고, 문자를 저장하려면 'char' 데이터 타입을 사용합니다.

```java
int age = 20;
char gender = 'F';
```

### 연산자 (Operators)

Java에서는 데이터를 처리하기 위해 다양한 연산자를 제공합니다.

- 산술 연산자: +, -, \*, /, % 등
- 비교 연산자: ==, !=, >, <, >=, <= 등
- 논리 연산자: &&, ||, ! 등
- 할당 연산자: =, +=, -=, \*=, /=, %= 등

예를 들어, 두 수의 합을 계산하려면 '+' 산술 연산자를 사용하고, 두 값이 같은지 비교하려면 '==' 비교 연산자를 사용합니다.

```java
int sum = 10 + 20; // 산술 연산자
boolean isEqual = (sum == 30); // 비교 연산자
```

## 마치며

Java에서의 데이터 타입, 변수, 연산자에 대해 알아봤습니다.

이들은 Java 프로그래밍의 기본적인 구성요소이므로 확실히 이해하고 있어야 합니다.
