---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Sharing_A_Pizza_3
title: Sharing a Pizza 3 (with.Java)
# title: Sharing a Pizza 1 (with.Java)
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
date: 2024-01-07 09:00:00 +0900
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

## "피자 나눠 먹기 2" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이네 피자가게는 피자를 여섯 조각으로 잘라 줍니다.

피자를 나눠먹을 사람의 수 n이 매개변수로 주어질 때, n명이 주문한 피자를 남기지 않고 모두 같은 수의 피자 조각을 먹어야 한다면 최소 몇 판을 시켜야 하는지를 return 하도록 solution 함수를 완성해보세요.

#### 입출력 예시

| n   | result |
| --- | ------ |
| 6   | 1      |
| 10  | 5      |
| 4   | 2      |

### 문제에 대한 나의 풀이

```java
class Solution {
	public int solution(int n) {
		int answer = 0;
		for (int i = 1; i <= 6 * n; i++) {
			if (6 * i % n == 0) {
				answer = i;
				break;
			}
		}
		return answer;
	}
}
```

#### 풀이 설명

int answer = 0;: 결과 값을 저장할 변수 answer를 초기화합니다.

for (int i = 1; i <= 6 _ n; i++) : i를 1부터 6의 배수로 6 _ n까지 반복합니다. 아무리 커도 6 \* n의 값을 넘지는 않을 것이기 때문입니다.

if (6 \* i % n == 0) : 현재 i에 대해 6을 곱한 값이 n으로 나누어 떨어지는지 확인합니다.

answer = i;: 만약 나누어 떨어진다면, answer에 현재의 i 값을 저장하고 반복문을 종료합니다.

break;: 조건을 만족하는 경우, 반복문을 종료합니다.

return answer;: 계산된 결과인 answer를 반환합니다.

이 코드는 n을 6의 배수 중에서 나누어 떨어지는 첫 번째 수를 찾는 것입니다.

만약 n이 6의 배수라면, answer는 1이 될 것이고, 그렇지 않으면 n의 배수 중에서 가장 작은 수가 answer로 반환됩니다.
