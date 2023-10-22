---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Count_Between_x
title: x 사이의 개수(with.Java)
# title: Count between x (with.Java)
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
date: 2023-10-21 09:00:00 +0900
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

### x 사이의 개수에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자열 myString이 주어집니다.

myString을 문자 "x"를 기준으로 나눴을 때 나눠진 문자열 각각의 길이를 순서대로 저장한 배열을 return 하는 solution 함수를 완성해 주세요.

##### 입출력 예시

"x"를 기준으로 문자열을 나누면 ["o", "oo", "o", "", "o", ""]가 됩니다.

각각의 길이로 배열을 만들면 [1, 2, 1, 0, 1, 0]입니다. 따라서 [1, 2, 1, 0, 1, 0]을 return 합니다.

#### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public int[] solution(String myString) {
        int[] answer;
        char[] c = new char[myString.length()];
        ArrayList<Integer> flag = new ArrayList<Integer>();
        for(int i = 0; i < myString.length(); i++){
            if(myString.charAt(i) == 'x'){
                flag.add(i);
            }
        }

        if(flag.get(flag.size() - 1) == myString.length() - 1 || flag.get(0) == 0){
            answer = new int[flag.size() + 1];
        } else {
            answer = new int[flag.size()];
        }

        for(int i = 0; i < flag.size(); i++){
            System.out.println(flag.get(i));
            if(i == 0){
                answer[i] = flag.get(i);
            }else{
                answer[i] = flag.get(i) - flag.get(i-1) - 1;
            }
        }
        answer[answer.length - 1] = myString.length() - 1 - flag.get(flag.size() - 1);
        return answer;
    }
}
```

##### 풀이 설명

처음에 위의 코드대로 테스트 문제를 해결하였으나 다른 테스트 케이스에선 통과하지 못했습니다. 통과하지 못한 이유에 대해선 아래와 같이 생각해보았습니다.

- 주어진 문자열 myString에서 "x"를 기준으로 문자열을 나누고, 각 부분 문자열의 길이를 저장해야 합니다.
- 코드에서는 "x"의 위치를 찾아 flag 리스트에 저장하고, 이를 기반으로 각 부분 문자열의 길이를 계산하려고 합니다. 하지만 코드에서 flag 리스트에 저장하는 위치는 "x" 문자의 위치가 아니라 "x"의 인덱스를 나타냅니다. 따라서 각 부분 문자열의 길이를 계산할 때 "x"의 위치와 인덱스 간에 차이가 발생하게 되어 예상치 못한 결과가 나타납니다.
- 예를 들어, "oxooxoxxox" 문자열에서 "x"의 위치는 [1, 3, 5, 6, 8]입니다. 그러나 코드에서는 flag 리스트에는 이 위치가 아니라 "x"의 인덱스인 [1, 2, 4, 5, 7]가 저장됩니다.
- 이로 인해 부분 문자열의 길이를 계산할 때, 인덱스 간의 차이를 구하므로 [1, 2, 1, 0, 2, 0]과 같이 예상치 못한 결과가 나타납니다.

즉, 문제를 해결하려면 "x"의 위치가 아니라 "x"를 기준으로 문자열을 나누고 각 부분 문자열의 길이를 계산해야 합니다.

아래는 자가 진단하고 새로 작성한 코드입니다.

###### 새로 작성한 코드

```java
import java.util.*;

class Solution {
    public int[] solution(String myString) {
        ArrayList<Integer> lengths = new ArrayList<Integer>();
        int length = 0;

        for (int i = 0; i < myString.length(); i++) {
            if (myString.charAt(i) == 'x') {
                lengths.add(length);
                length = 0;
            } else {
                length++;
            }
        }

        lengths.add(length); // 마지막 부분 문자열의 길이 추가

        int[] answer = new int[lengths.size()];
        for (int i = 0; i < lengths.size(); i++) {
            answer[i] = lengths.get(i);
        }

        return answer;
    }
}
```

###### 수정한 코드 풀이

ArrayList<Integer> lengths = new ArrayList<Integer>();: 부분 문자열의 길이를 저장할 리스트 lengths를 생성합니다.

int length = 0;: 현재 부분 문자열의 길이를 저장하는 변수 length를 초기화합니다.

for (int i = 0; i < myString.length(); i++) { ... }: 주어진 문자열 myString을 한 글자씩 순회하는 반복문을 시작합니다.

if (myString.charAt(i) == 'x') { ... }: 현재 문자가 "x"인지 확인합니다. 만약 "x"라면 현재까지의 부분 문자열의 길이를 lengths 리스트에 추가하고 length 변수를 0으로 초기화합니다.

"x"가 아닌 문자열을 만나면 length 값을 1씩 증가시킵니다.

반복문을 통해 문자열을 순회하면서 "x"를 기준으로 부분 문자열의 길이를 올바르게 계산하고 lengths 리스트에 저장합니다.

lengths.add(length);: 마지막 부분 문자열의 길이를 lengths 리스트에 추가합니다.

int[] answer = new int[lengths.size()];: 길이가 정해진 lengths 리스트를 기반으로 결과 배열 answer를 생성합니다.

for (int i = 0; i < lengths.size(); i++) { ... }: lengths 리스트에 저장된 부분 문자열의 길이를 answer 배열에 복사합니다.

함수가 종료되고 answer 배열을 반환합니다. 이 배열에는 "x"를 기준으로 나눈 각 부분 문자열의 길이가 순서대로 저장되어 있습니다.
