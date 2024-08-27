---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_SQL_Identifiers
title: About SQL Identifiers
# title: About SQL Identifiers
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
date: 2024-08-27 09:00:00 +0900
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

## SQL의 식별자에 대하여 알아본 글입니다.

안녕하세요!

오늘은 SQL(Structured Query Language)에서 관계에 대해 알아보겠습니다.

SQL은 데이터베이스에서 데이터를 관리하고 조작하기 위해 사용되는 강력한 언어로, 관계형 데이터베이스에서 데이터 간의 관계를 표현하고 처리하는 데 중요한 역할을 합니다.

이번 포스팅에서는 SQL에서 관계를 표현하는 방법과 관련된 주요 개념들을 살펴보겠습니다.

{:data-align="center"}

<!-- outline-end -->

## 관계형 데이터베이스 모델

### 개요

관계형 데이터베이스 모델은 데이터를 테이블 형식으로 저장하고 관리하는 방식입니다.

이 모델에서는 각 테이블이 엔터티를 나타내며, 테이블 간의 관계를 통해 데이터를 조직화하고 관리합니다.

### 예시

- **학생(Student) 테이블**: 학생의 학번, 이름, 전공 등의 정보를 저장합니다.
- **과목(Subject) 테이블**: 과목의 코드, 이름, 담당 교수 등의 정보를 저장합니다.
- **수강(Enrollment) 테이블**: 학생과 과목 간의 수강 관계를 저장합니다.

## 관계 표현 방법

### 기본 키 (Primary Key)

기본 키는 각 테이블의 레코드를 고유하게 식별하는 데 사용되는 속성입니다.

기본 키는 테이블에 있는 각 레코드를 고유하게 식별할 수 있어야 하며, NULL 값을 가질 수 없습니다.

```sql
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(50),
    Major VARCHAR(50)
);

CREATE TABLE Subjects (
    SubjectID INT PRIMARY KEY,
    Name VARCHAR(50),
    Professor VARCHAR(50)
);
```

### 외래 키 (Foreign Key)

외래 키는 다른 테이블의 기본 키를 참조하는 속성입니다.

이를 통해 테이블 간의 관계를 설정하고 관리할 수 있습니다.

```sql
CREATE TABLE Enrollments (
    EnrollmentID INT PRIMARY KEY,
    StudentID INT,
    SubjectID INT,
    FOREIGN KEY (StudentID) REFERENCES Students(StudentID),
    FOREIGN KEY (SubjectID) REFERENCES Subjects(SubjectID)
);
```

## 관계 유형

### 일대일 관계 (One-to-One Relationship)

한 엔터티의 레코드가 다른 엔터티의 레코드와 하나씩만 연결되는 관계입니다.

### 일대다 관계 (One-to-Many Relationship)

한 엔터티의 레코드가 다른 엔터티의 레코드와 여러 개 연결되는 관계입니다.

### 다대다 관계 (Many-to-Many Relationship)

다수의 엔터티의 레코드가 다른 엔터티의 레코드와 여러 개 연결되는 관계입니다.

이 관계는 중간 테이블을 사용하여 구현됩니다.

## SQL에서의 관계 조작

### 조인 (JOIN)

조인은 두 개 이상의 테이블을 연결하여 데이터를 검색하고 결합하는 데 사용됩니다.

```sql
SELECT Students.Name, Subjects.Name
FROM Students
JOIN Enrollments ON Students.StudentID = Enrollments.StudentID
JOIN Subjects ON Enrollments.SubjectID = Subjects.SubjectID;
```

### 서브쿼리 (Subquery)

서브쿼리는 하위 쿼리로, 다른 쿼리의 결과를 검색하여 사용하는 데 사용됩니다.

```sql
SELECT Name
FROM Students
WHERE StudentID IN (SELECT StudentID FROM Enrollments WHERE SubjectID = 1);
```

## 마치며

SQL에서는 관계형 데이터베이스 모델을 사용하여 데이터 간의 관계를 표현하고 처리합니다.

기본 키와 외래 키를 사용하여 테이블 간의 관계를 설정하고, 조인과 서브쿼리를 사용하여 데이터를 검색하고 조작합니다.

관계형 데이터베이스 모델을 이해하고 SQL에서의 관계를 효과적으로 다루기 위해서는 기본 키, 외래 키, 다양한 관계 유형에 대한 이해가 필요합니다.

이를 통해 데이터베이스에서 복잡한 관계를 효율적으로 다룰 수 있고, 원하는 정보를 정확하게 추출할 수 있습니다.

이번 포스팅에서는 SQL에서의 관계에 대해 간략히 살펴보았습니다.

다음 포스팅에서는 SQL에서의 조인과 서브쿼리에 대해 더 자세히 다뤄보겠습니다.

계속해서 관심 가져주시면 감사하겠습니다!
