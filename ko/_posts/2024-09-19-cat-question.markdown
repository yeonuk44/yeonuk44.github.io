---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Cat_Question
title: 백준 10171번, 고양이 (with.Java)
# title: Baekjun 10171, Cat (with.Java)
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
date: 2024-09-19 09:00:00 +0900
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

## 백준 10171번 고양이 (with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

아래 예제와 같이 고양이를 출력하시오.

#### 입력

없음.

#### 출력

고양이를 출력한다.

### 문제 풀이

```java
class Main {
	public static void main(String[] args) {

		System.out.println("\\    /\\");
		System.out.println(" )  ( ')");
		System.out.println("(  /  )");
		System.out.println(" \\(__)|");

	}
}

```

#### 풀이 설명

`\\는 \를 출력합니다.
()는 괄호를 출력합니다.
|는 파이프를 출력합니다.`

이 코드는 이스케이프 시퀀스를 사용하여 특수 문자를 출력하고, 각각의 System.out.println 문은 한 줄씩 출력합니다.

문제를 풀며 이스케이프 시퀀스에 대해 알고 있어야 풀이가 가능했음을 알았습니다.

이스케이프 시퀀스란
이스케이프 시퀀스(Escape Sequence)는 문자열 내에서 특수한 의미를 갖는 문자를 표현하기 위해 사용됩니다. 이는 주로 제어 문자 또는 특수 문자를 문자열에 포함시킬 때 사용됩니다. 이스케이프 시퀀스는 백슬래시(`\`)로 시작하며, 뒤에 오는 문자에 따라 다양한 기능을 수행합니다.

주요 이스케이프 시퀀스

`\\ : 백슬래시 (\) 자체를 의미합니다.
\' : 작은따옴표 (')를 의미합니다.
\" : 큰따옴표 (")를 의미합니다.
\n : 줄 바꿈 (새로운 줄로 이동)
\t : 탭 문자 (일반적으로 4 또는 8 스페이스)
\r : 캐리지 리턴 (줄의 시작으로 이동)
\b : 백스페이스 (이전 문자 삭제)
\f : 폼 피드 (페이지 나누기)
\uXXXX : 유니코드 문자 (XXXX는 4자리 16진수)`

### 결론

코드에서 특수한 의미를 갖는 문자를 표현할 때 큰따옴표(")와 역슬래쉬(`\`)가 포함되어 있다면 특수한 의미의 문자 앞에 역슬래쉬 1개를 붙여주면 됩니다.

감사합니다!
