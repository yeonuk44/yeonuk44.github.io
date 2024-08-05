---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_H_Index
title: H-Index (with.Java)
# title: Letter (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, sort]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-08-05 09:00:00 +0900
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

## H-Index (with.Java) 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고를 해보고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

H-Index는 과학자의 생산성과 영향력을 나타내는 지표입니다.

어느 과학자의 H-Index를 나타내는 값인 h를 구하려고 합니다.

위키백과1에 따르면, H-Index는 다음과 같이 구합니다.

어떤 과학자가 발표한 논문 n편 중, h번 이상 인용된 논문이 h편 이상이고 나머지 논문이 h번 이하 인용되었다면 h의 최댓값이 이 과학자의 H-Index입니다.

어떤 과학자가 발표한 논문의 인용 횟수를 담은 배열 citations가 매개변수로 주어질 때, 이 과학자의 H-Index를 return 하도록 solution 함수를 작성해주세요.

#### 제한사항

- 과학자가 발표한 논문의 수는 1편 이상 1,000편 이하입니다.
- 논문별 인용 횟수는 0회 이상 10,000회 이하입니다.

#### 입출력 예시

| citations       | return |
| --------------- | ------ |
| [3, 0, 6, 1, 5] | 3      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
import java.util.Arrays;

class Solution {
    public int solution(int[] citations) {
        int answer = 0;
        Arrays.sort(citations);
        for(int i = 0; i < citations.length; i++){
            int temp = Math.min(citations[i], citations.length - i);
            if(temp >= answer){
                answer = temp;
            }else{
                break;
            }
        }
        return answer;
    }
}
```

### 풀이 설명

- solution 메서드는 정수 배열 citations를 입력으로 받습니다.
- 우선 citations 배열을 오름차순으로 정렬합니다. 이는 H-Index를 계산하기 위해 배열을 정렬하는 일반적인 접근 방법입니다.
- 그런 다음 for 루프를 사용하여 배열을 순회합니다.
- 각 인용 횟수 citations[i]와 남은 논문 수인 citations.length - i 중 작은 값을 선택합니다. 이 값이 현재의 H-Index 후보가 됩니다.
- 현재 H-Index 후보가 이전의 H-Index 후보보다 크거나 같다면 answer를 업데이트합니다.
- 이후의 값들은 더 작아지므로, 더 이상 H-Index가 증가하지 않는다는 것을 의미합니다. 따라서 break를 사용하여 반복문을 종료합니다.
- 최종적으로 answer를 반환합니다.

### 결론

이 코드는 논문 인용 횟수 배열을 사용하여 H-Index를 계산하는 문제를 해결하는데, 배열을 정렬한 후에 반복문을 사용하여 H-Index 후보를 찾고 이를 검증하는 방식을 사용합니다.
