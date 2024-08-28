---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_SQL_Identifiers_Features
title: SQL의 식별자 특징에 대하여
# title: About SQL Identifier Features
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: DB
# multiple tag entries are possible
tags: [db]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-08-28 09:00:00 +0900
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

## SQL의 식별자 특징에 대하여 알아본 글입니다.

안녕하세요!

오늘은 SQL(Structured Query Language)에서의 식별자에 대해 알아보겠습니다.

SQL에서 식별자는 데이터베이스 내에서 데이터를 고유하게 식별하는 데 사용되는 중요한 개념입니다.

이번 포스팅에서는 SQL에서의 식별자의 종류와 사용 방법에 대해 자세히 살펴보겠습니다.

{:data-align="center"}

<!-- outline-end -->

## 기본 키 (Primary Key)

### 개요

기본 키는 각 행을 고유하게 식별하는 데 사용되는 필드입니다.

각 테이블은 하나의 기본 키를 가질 수 있으며, 이는 해당 테이블의 각 행을 고유하게 식별하는 데 사용됩니다.

### 사용 방법

기본 키는 보통 AUTO_INCREMENT 또는 IDENTITY와 같은 자동 증가 값을 가지며, 각 행이 추가될 때마다 자동으로 증가합니다.

```sql
CREATE TABLE Students (
    StudentID INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(50),
    Major VARCHAR(50)
);
```

## 외래 키 (Foreign Key)

### 개요

외래 키는 다른 테이블의 기본 키를 참조하는 필드입니다.

이를 통해 두 테이블 간의 관계를 설정하고 유지할 수 있습니다.

### 사용 방법

외래 키는 다른 테이블의 기본 키를 참조하여 생성됩니다.

이를 통해 부모 테이블과 자식 테이블 간의 관계를 설정할 수 있습니다.

```sql
CREATE TABLE Enrollments (
    EnrollmentID INT PRIMARY KEY AUTO_INCREMENT,
    StudentID INT,
    SubjectID INT,
    FOREIGN KEY (StudentID) REFERENCES Students(StudentID),
    FOREIGN KEY (SubjectID) REFERENCES Subjects(SubjectID)
);
```

## 유니크 키 (Unique Key)

### 개요

유니크 키는 테이블 내에서 중복을 허용하지 않는 필드입니다.

각 행의 값이 유일해야 하지만, 기본 키와는 달리 NULL 값을 가질 수 있습니다.

### 사용 방법

유니크 키는 각 행의 값이 중복되지 않아야 하며, NULL 값을 가질 수 있습니다.

이를 통해 특정 필드가 중복되지 않도록 보장할 수 있습니다.

```sql
CREATE TABLE Users (
    UserID INT PRIMARY KEY AUTO_INCREMENT,
    Username VARCHAR(50) UNIQUE,
    Email VARCHAR(50) UNIQUE
);
```

## 마치며

SQL에서의 식별자는 데이터를 고유하게 식별하는 데 필수적인 요소입니다.

기본 키, 외래 키, 유니크 키 등 다양한 종류의 식별자를 적절히 활용하여 데이터베이스의 정확성과 일관성을 유지할 수 있습니다.

데이터베이스 설계 시 식별자를 잘 선택하고 활용하여 효율적인 데이터 관리를 할 수 있도록 노력해 보세요.

이번 포스팅이 SQL에서의 식별자에 대해 이해하는 데 도움이 되었기를 바랍니다.

감사합니다!
