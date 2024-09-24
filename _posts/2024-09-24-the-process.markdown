---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_The_Process
title: Process (with. Java)
# title: Process (with. Java)
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
date: 2024-09-24 09:00:00 +0900
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

## 프로세스(with. Java)에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

괄호가 바르게 짝지어졌다는 것은 '(' 문자로 열렸으면 반드시 짝지어서 ')' 문자로 닫혀야 한다는 뜻입니다. 예를 들어

```bash
"()()" 또는 "(())()" 는 올바른 괄호입니다.
")()(" 또는 "(()(" 는 올바르지 않은 괄호입니다.
'(' 또는 ')' 로만 이루어진 문자열 s가 주어졌을 때, 문자열 s가 올바른 괄호이면 true를 return 하고, 올바르지 않은 괄호이면 false를 return 하는 solution 함수를 완성해 주세요.
```

#### 제한사항

- 문자열 s의 길이 : 100,000 이하의 자연수
- 문자열 s는 '(' 또는 ')' 로만 이루어져 있습니다.

#### 입출력 예

| s        | answer |
| -------- | ------ |
| "()()"   | true   |
| "(())()" | true   |
| ")()("   | false  |
| "(()("   | false  |

### 문제 풀이

```java
import java.util.ArrayDeque;
import java.util.Deque;

class Solution {
    boolean solution(String s) {
        Deque<Character> deque = new ArrayDeque<>();
        for(int i = 0; i < s.length(); i++){
            deque.offer(s.charAt(i));
        }

        int count = 0;
        int size = deque.size();
        if(deque.peek() == ')' || deque.peekLast() == '('){
            return false;
        }else{
            while(!deque.isEmpty()){
                if(count < 0 || count > deque.size()){
                    return false;
                }else{
                    if(deque.poll() == '('){
                        count++;
                    }else{
                        count--;
                    }
                }
            }
        }

        return true;
    }
}
```

#### 풀이 설명

이 코드는 문자열 s가 올바른 괄호 문자열인지 확인하는 것입니다.

올바른 괄호 문자열은 여는 괄호 '('가 항상 닫는 괄호 ')'보다 먼저 등장하고, 여는 괄호의 개수와 닫는 괄호의 개수가 동일해야 합니다.

코드는 Deque를 이용하여 문자열을 처리하고 이를 통해 괄호의 유효성을 검사합니다.

아래는 코드의 각 부분을 설명한 풀이 리뷰입니다.

Deque 초기화와 문자열 저장:

Deque<Character> deque = new ArrayDeque<>();
문자열 s의 각 문자를 Deque에 저장합니다.

Deque는 양방향 큐로, 문자 삽입과 삭제에 유리합니다.

Deque에 문자열 문자 추가:

for (int i = 0; i < s.length(); i++) { deque.offer(s.charAt(i)); }
문자열의 각 문자를 Deque에 추가하여 순차적으로 처리할 준비를 합니다.

초기 조건 검사:

if (deque.peek() == ')' || deque.peekLast() == '(') { return false; }
Deque의 첫 번째 문자가 ')'이거나 마지막 문자가 '('이면, 올바른 괄호 문자열이 될 수 없으므로 즉시 false를 반환합니다.

괄호의 유효성 검사:

while (!deque.isEmpty()) { ... }
Deque가 빌 때까지 반복합니다.

count 변수를 사용하여 여는 괄호와 닫는 괄호의 균형을 맞춥니다.

여는 괄호 '('는 count를 증가시키고, 닫는 괄호 ')'는 count를 감소시킵니다.

균형 검사:

if (count < 0 || count > deque.size()) { return false; }
count가 0보다 작거나 남은 Deque의 크기보다 크면 올바른 괄호 문자열이 아닙니다.

여는 괄호가 너무 많거나 닫는 괄호가 너무 많으면 false를 반환합니다.

최종 반환 값:

모든 문자를 처리한 후 count가 0이면 올바른 괄호 문자열이므로 true를 반환하고, 그렇지 않으면 false를 반환합니다.

문제점 및 개선점

초기 조건 검사:
Deque를 사용하여 문자열을 저장하고 조건을 검사하는 대신, 바로 문자열을 검사할 수 있습니다.

예를 들어, 첫 번째 문자가 ')'이거나 마지막 문자가 '('인지를 먼저 검사하면 Deque를 사용할 필요가 없습니다.

Deque의 불필요한 사용:
Deque를 사용하지 않고, 단순히 문자열을 순차적으로 처리하면서 여는 괄호와 닫는 괄호의 균형을 맞출 수 있습니다.

개선된 접근 방식

Deque를 사용하지 않고, 간단하게 count 변수를 이용하여 여는 괄호와 닫는 괄호의 균형을 맞추는 방법이 더 효율적입니다.

```java
class Solution {
    boolean solution(String s) {
        int count = 0;

        for (char c : s.toCharArray()) {
            if (c == '(') {
                count++;
            } else {
                count--;
            }

            if (count < 0) {
                return false;
            }
        }

        return count == 0;
    }
}

```

이렇게 하면 코드가 더 간결해지고, Deque를 사용하지 않아도 되므로 성능이 개선됩니다.
