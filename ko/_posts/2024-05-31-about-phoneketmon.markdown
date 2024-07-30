---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Phoneketmon
title: 폰켓몬 (with.Java)
# title: Phoneketmon (with.Java)
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, hash]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-05-31 09:00:00 +0900
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

## "폰켓몬 (with.Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

당신은 폰켓몬을 잡기 위한 오랜 여행 끝에, 홍 박사님의 연구실에 도착했습니다.

홍 박사님은 당신에게 자신의 연구실에 있는 총 N 마리의 폰켓몬 중에서 N/2마리를 가져가도 좋다고 했습니다.

홍 박사님 연구실의 폰켓몬은 종류에 따라 번호를 붙여 구분합니다. 따라서 같은 종류의 폰켓몬은 같은 번호를 가지고 있습니다.

예를 들어 연구실에 총 4마리의 폰켓몬이 있고, 각 폰켓몬의 종류 번호가 [3번, 1번, 2번, 3번]이라면 이는 3번 폰켓몬 두 마리, 1번 폰켓몬 한 마리, 2번 폰켓몬 한 마리가 있음을 나타냅니다.

이때, 4마리의 폰켓몬 중 2마리를 고르는 방법은 다음과 같이 6가지가 있습니다.

- 첫 번째(3번), 두 번째(1번) 폰켓몬을 선택
- 첫 번째(3번), 세 번째(2번) 폰켓몬을 선택
- 첫 번째(3번), 네 번째(3번) 폰켓몬을 선택
- 두 번째(1번), 세 번째(2번) 폰켓몬을 선택
- 두 번째(1번), 네 번째(3번) 폰켓몬을 선택
- 세 번째(2번), 네 번째(3번) 폰켓몬을 선택

이때, 첫 번째(3번) 폰켓몬과 네 번째(3번) 폰켓몬을 선택하는 방법은 한 종류(3번 폰켓몬 두 마리)의 폰켓몬만 가질 수 있지만, 다른 방법들은 모두 두 종류의 폰켓몬을 가질 수 있습니다.

따라서 위 예시에서 가질 수 있는 폰켓몬 종류 수의 최댓값은 2가 됩니다.

당신은 최대한 다양한 종류의 폰켓몬을 가지길 원하기 때문에, 최대한 많은 종류의 폰켓몬을 포함해서 N/2마리를 선택하려 합니다.

N마리 폰켓몬의 종류 번호가 담긴 배열 nums가 매개변수로 주어질 때, N/2마리의 폰켓몬을 선택하는 방법 중, 가장 많은 종류의 폰켓몬을 선택하는 방법을 찾아, 그때의 폰켓몬 종류 번호의 개수를 return 하도록 solution 함수를 완성해주세요.

#### 제한사항

- nums는 폰켓몬의 종류 번호가 담긴 1차원 배열입니다.
- nums의 길이(N)는 1 이상 10,000 이하의 자연수이며, 항상 짝수로 주어집니다.
- 폰켓몬의 종류 번호는 1 이상 200,000 이하의 자연수로 나타냅니다.
- 가장 많은 종류의 폰켓몬을 선택하는 방법이 여러 가지인 경우에도, 선택할 수 있는 폰켓몬 종류 개수의 최댓값 하나만 return 하면 됩니다.

#### 입출력 예시

<!--
| lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| nums               | result |
| ------------------ | ------ |
| [3, 1, 2, 3]       | 2      |
| [3, 3, 3, 2, 2, 4] | 3      |
| [3, 3, 3, 2, 2, 2] | 2      |

### 문제에 대한 나의 풀이

```java
import java.util.Arrays;
class Solution {
    public int solution(int[] nums) {
        int answer = 0;
        int choiceNum = nums.length / 2;
        nums = Arrays.stream(nums).distinct().toArray();

        if(nums.length >= choiceNum){
            return choiceNum;
        }else{
            return nums.length;
        }
    }
}
```

### 풀이 리뷰

solution 메서드는 정수 배열 nums를 입력으로 받습니다.

choiceNum 변수를 선언하고, 배열의 길이의 절반을 저장합니다. 이는 선택할 수 있는 숫자의 최대 개수를 나타냅니다.

Arrays.stream(nums).distinct().toArray()를 사용하여 중복된 숫자를 제거한 후, 배열로 변환하여 nums에 저장합니다.

if 문을 사용하여 중복이 제거된 배열의 길이가 choiceNum보다 크거나 같으면 choiceNum을 반환합니다. 이는 중복이 제거된 배열의 길이가 선택할 수 있는 최대 숫자의 개수보다 크다는 것을 의미합니다.

그렇지 않은 경우에는 중복이 제거된 배열의 길이를 반환합니다.

최종적으로 선택된 숫자의 개수를 반환합니다.

이 코드는 배열에서 중복된 숫자를 제거하고, 선택할 수 있는 숫자의 최대 개수를 기준으로 서로 다른 숫자의 개수를 반환하는 간단한 방법을 사용합니다.
