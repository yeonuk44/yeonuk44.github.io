---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Coffee_Errand
title: 커피 심부름(with.Java)
# title: Coffee Errand (with.Java)
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
date: 2023-11-29 09:00:00 +0900
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

## "커피 심부름" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

팀의 막내인 철수는 아메리카노와 카페 라테만 판매하는 카페에서 팀원들의 커피를 사려고 합니다.

아메리카노와 카페 라테의 가격은 차가운 것과 뜨거운 것 상관없이 각각 4500, 5000원입니다.

각 팀원에게 마실 메뉴를 적어달라고 하였고, 그 중에서 메뉴만 적은 팀원의 것은 차가운 것으로 통일하고 "아무거나"를 적은 팀원의 것은 차가운 아메리카노로 통일하기로 하였습니다.

각 직원이 적은 메뉴가 문자열 배열 order로 주어질 때, 카페에서 결제하게 될 금액을 return 하는 solution 함수를 작성해주세요.

order의 원소는 아래의 것들만 들어오고, 각각의 의미는 다음과 같습니다.

order의 원소 의미

"iceamericano", "americanoice" 차가운 아메리카노

"hotamericano", "americanohot" 따뜻한 아메리카노

"icecafelatte", "cafelatteice" 차가운 카페 라테

"hotcafelatte", "cafelattehot" 따뜻한 카페 라테

"americano" 아메리카노

"cafelatte" 카페 라테

"anything" 아무거나

#### 입출력 예시

| order                                                     | result |
| --------------------------------------------------------- | ------ |
| ["cafelatte", "americanoice", "hotcafelatte", "anything"] | 19000  |
| ["americanoice", "americano", "iceamericano"]             | 13500  |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String[] order) {
        int answer = 0;
        for(String temp: order){
            if(temp.contains("americano")){
                answer += 4500;
            } else if(temp.contains("cafelatte")){
                answer += 5000;
            } else {
                answer += 4500;
            }
        }
        return answer;
    }
}
```

#### 풀이 설명

int answer = 0;: 결과를 저장할 정수형 변수 answer를 초기화합니다.

for(String temp : order) : 문자열 배열 order를 반복하면서 각 주문 temp를 검사합니다.

if(temp.contains("americano")) : 만약 주문에 "americano"라는 문자열이 포함되어 있다면:

가격을 4500 추가합니다.

else if(temp.contains("cafelatte")) : 만약 주문에 "cafelatte"라는 문자열이 포함되어 있다면:

가격을 5000 추가합니다.

else : 그 외의 경우 (다른 음료인 경우):

가격을 4500 추가합니다.

return answer;: 모든 주문에 대한 가격을 계산한 후에 answer를 반환합니다.
