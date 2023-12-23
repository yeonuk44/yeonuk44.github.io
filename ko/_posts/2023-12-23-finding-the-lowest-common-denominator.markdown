---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Finding_The_Lowest_Common_Denominator
title: 최빈값 구하기(with.Java)
# title: Finding the Lowest Common Denominator (with.Java)
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
date: 2023-12-23 09:00:00 +0900
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

## "최빈값 구하기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

최빈값은 주어진 값 중에서 가장 자주 나오는 값을 의미합니다.

정수 배열 array가 매개변수로 주어질 때, 최빈값을 return 하도록 solution 함수를 완성해보세요.

최빈값이 여러 개면 -1을 return 합니다.

#### 입출력 예시

| array              | result |
| ------------------ | ------ |
| [1, 2, 3, 3, 3, 4] | 3      |
| [1, 1, 2, 2]       | -1     |
| [1 ]               | 1      |

### 문제에 대한 나의 풀이

```java
import java.util.Map;
import java.util.HashMap;

class Solution {
    public int solution(int[] array) {
        Map<Integer, Integer> frequencyMap = new HashMap<>();
        for (int num : array) {
            frequencyMap.put(num, frequencyMap.getOrDefault(num, 0) + 1);
        }

        int mode = -1;
        int maxFrequency = 0;

        for (Map.Entry<Integer, Integer> entry : frequencyMap.entrySet()) {
            int num = entry.getKey();
            int frequency = entry.getValue();

            if (frequency > maxFrequency) {
                mode = num;
                maxFrequency = frequency;
            }else if(frequency == maxFrequency){
                mode = -1;
            }
        }
        return mode;
    }
}
```

#### 풀이 설명

import java.util.Map;, import java.util.HashMap;: Map과 HashMap 클래스를 사용하기 위해 import 문을 추가합니다.

public int solution(int[] array) : 함수 solution을 선언하고, 정수 배열 array를 입력 매개변수로 받습니다. 이 함수는 정수 값을 반환합니다.

Map<Integer, Integer> frequencyMap = new HashMap<>();: 정수 값과 해당 값의 빈도수를 저장하는 frequencyMap이라는 HashMap을 생성합니다. 이 맵은 정수를 키(key)로 사용하고, 해당 정수의 빈도수를 값(value)로 저장합니다.

for (int num : array) : 배열 array의 각 요소를 반복하면서 아래의 작업을 수행합니다.

frequencyMap.put(num, frequencyMap.getOrDefault(num, 0) + 1);: 현재 요소 num을 키로 하여 frequencyMap에서 해당 키의 값을 가져온 후, getOrDefault를 사용하여 값이 없을 경우 0을 기본값으로 설정하고 1을 더하여 빈도수를 업데이트합니다. 이렇게 하면 배열에 등장한 각 숫자의 빈도수가 맵에 기록됩니다.

int mode = -1;, int maxFrequency = 0;: 최빈값(mode)과 그 빈도수를 저장할 변수를 초기화합니다. mode를 -1로 초기화하고, maxFrequency를 0으로 초기화합니다.

for (Map.Entry<Integer, Integer> entry : frequencyMap.entrySet()) : frequencyMap의 각 항목에 대해 반복하면서 아래의 작업을 수행합니다.

int num = entry.getKey();, int frequency = entry.getValue();: 현재 항목의 키와 값을 가져옵니다. num은 숫자를 나타내고, frequency는 해당 숫자의 빈도수를 나타냅니다.

if (frequency > maxFrequency) : 현재 숫자의 빈도수가 최대 빈도수보다 큰 경우, 아래의 작업을 수행합니다.

mode = num;: mode 변수를 현재 숫자로 업데이트합니다.

maxFrequency = frequency;: 최대 빈도수를 현재 빈도수로 업데이트합니다.

else if (frequency == maxFrequency) : 현재 숫자의 빈도수가 최대 빈도수와 같은 경우, 중복된 최빈값이 존재함을 나타냅니다.

mode = -1;: mode 변수를 -1로 설정하여 중복된 최빈값이 있는 경우를 나타냅니다.

return mode;: 최빈값(mode)을 함수의 반환 값으로 반환합니다.
