---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Joystick
title: 조이스틱 (with.Java)
# title: Joystick (with.Java)
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
date: 2024-08-14 09:00:00 +0900
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

## 조이스틱 (with.Java) 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고를 해보고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

조이스틱으로 알파벳 이름을 완성하세요.

맨 처음엔 A로만 이루어져 있습니다.

ex. 완성해야 하는 이름이 세 글자면 AAA, 네 글자면 AAAA

조이스틱을 각 방향으로 움직이면 아래와 같습니다.

▲ - 다음 알파벳

▼ - 이전 알파벳 (A에서 아래쪽으로 이동하면 Z로)

◀ - 커서를 왼쪽으로 이동 (첫 번째 위치에서 왼쪽으로 이동하면 마지막 문자에 커서)

▶ - 커서를 오른쪽으로 이동 (마지막 위치에서 오른쪽으로 이동하면 첫 번째 문자에 커서)

예를 들어 아래의 방법으로 "JAZ"를 만들 수 있습니다.

- 첫 번째 위치에서 조이스틱을 위로 9번 조작하여 J를 완성합니다.
- 조이스틱을 왼쪽으로 1번 조작하여 커서를 마지막 문자 위치로 이동시킵니다.
- 마지막 위치에서 조이스틱을 아래로 1번 조작하여 Z를 완성합니다.

따라서 11번 이동시켜 "JAZ"를 만들 수 있고, 이때가 최소 이동입니다.

만들고자 하는 이름 name이 매개변수로 주어질 때, 이름에 대해 조이스틱 조작 횟수의 최솟값을 return 하도록 solution 함수를 만드세요.

#### 제한사항

- name은 알파벳 대문자로만 이루어져 있습니다.
- name의 길이는 1 이상 20 이하입니다.

#### 입출력 예시

| name     | return |
| -------- | ------ |
| "JEROEN" | 56     |
| "JAN"    | 23     |

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(String name) {
        int answer = 0;
        int cursor = name.length() - 1;

        for(int i = 0; i < name.length(); i++){
            answer += Math.min(name.charAt(i) - 'A', 'Z' - name.charAt(i) + 1);
            if(i < name.length() - 1 && name.charAt(i + 1) == 'A'){
                int temp = i + 1;
                while(temp < name.length() && name.charAt(temp) == 'A'){
                    temp++;
                }
                cursor = Math.min(cursor, (i * 2) + (name.length() - temp));
                cursor = Math.min(cursor, i + (name.length() - temp) * 2);
            }
        }
        return answer + cursor;
    }
}
```

### 풀이 설명

먼저, answer 변수는 각 문자를 조작하여 만들어야 하는 문자열의 조작 횟수를 누적하는 변수입니다.

문자열을 처음부터 끝까지 반복하면서 각 문자를 조사합니다.

현재 문자에서 'A'까지의 거리와 'Z'에서 현재 문자까지의 거리 중 작은 값을 선택하여 해당 문자를 조작하는 데 필요한 최소한의 조작 횟수를 계산합니다.

예를 들어, 현재 문자가 'B'라면, 'A'까지는 한 칸 위로 조작하면 되므로 1번의 조작이 필요합니다.

또는 'Y'에서 'Z'까지 한 칸 아래로 조작하면 되므로 마찬가지로 1번의 조작이 필요합니다.

이런 식으로 각 문자마다 조작 횟수를 계산하여 answer 변수에 누적합니다.

그 다음으로, 연속된 'A'를 만나는 경우 추가적인 이동 횟수를 계산합니다.

'A'로 이어지는 부분을 만나면 그 다음으로 이동할 때 추가적인 조작 횟수를 고려해야 합니다.

왜냐하면 연속된 'A'를 만나면 되돌아갈 때에도 조작 횟수가 발생하기 때문입니다.

따라서 현재 문자 다음에 연속된 'A'를 만나면, 그 다음으로 이동할 때까지의 추가적인 조작 횟수를 계산합니다.

이를 위해 cursor 변수를 사용합니다.

cursor 변수는 연속된 'A'를 만나고 다음으로 이동할 때의 최소한의 추가 조작 횟수를 저장합니다.

이를 초기화하기 위해 cursor를 name의 길이 - 1로 초기화합니다.

이는 문자열 끝까지 한 번 이동하는 것이 최악의 경우라고 가정하기 때문입니다.

연속된 'A'를 만나는 경우, 그 다음으로 이동할 때까지의 조작 횟수를 계산합니다.

이 때, 두 가지 경우를 비교하여 더 작은 값을 선택합니다.

현재 문자 위치 i에서 연속된 'A'가 끝나는 위치까지 이동한 후, 끝에서부터 현재 위치까지의 거리와 현재 위치까지의 거리를 더합니다.

또는, 현재 위치까지의 거리와 연속된 'A'가 끝나는 위치부터 끝까지 이동한 후 다시 되돌아올 때까지의 거리를 더합니다.

이 경우, 현재 위치까지의 거리에다가 연속된 'A'가 끝나는 위치부터 끝까지의 거리를 두 배로 곱한 값을 더합니다.

이렇게 계산된 추가적인 이동 횟수를 cursor 변수에 저장합니다.

마지막으로, answer에 누적된 문자 조작 횟수와 추가적인 이동 횟수(cursor)를 더하여 최종적인 조작 횟수를 반환합니다.

### 결론

이러한 방식으로 주어진 문자열을 조작하여 목표 문자열로 만들기 위한 최소한의 조작 횟수를 계산합니다.
