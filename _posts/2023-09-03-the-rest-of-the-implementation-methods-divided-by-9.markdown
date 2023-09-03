---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Rest_Of_The_Implementation_Methods_Divided_By_9
title: For the rest of the implementation methods divided by 9 (with. Java)
# title: For the rest of the implementation methods divided by 9 (with. Java)

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
date: 2023-09-03 09:00:00 +0900
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

### 여러 조건에 의한 결과값 제어하는 방법에 대하여(주사위 게임 3, with.Java)

{:data-align="center"}

<!-- outline-end -->

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.
문제에 대해 먼저 알아보겠습니다.

#### 문제

1부터 6까지 숫자가 적힌 주사위가 네 개 있습니다. 네 주사위를 굴렸을 때 나온 숫자에 따라 다음과 같은 점수를 얻습니다.

네 주사위에서 나온 숫자가 모두 p로 같다면 1111 × p점을 얻습니다.
세 주사위에서 나온 숫자가 p로 같고 나머지 다른 주사위에서 나온 숫자가 q(p ≠ q)라면 (10 × p + q)2 점을 얻습니다.
주사위가 두 개씩 같은 값이 나오고, 나온 숫자를 각각 p, q(p ≠ q)라고 한다면 (p + q) × |p - q|점을 얻습니다.
어느 두 주사위에서 나온 숫자가 p로 같고 나머지 두 주사위에서 나온 숫자가 각각 p와 다른 q, r(q ≠ r)이라면 q × r점을 얻습니다.
네 주사위에 적힌 숫자가 모두 다르다면 나온 숫자 중 가장 작은 숫자 만큼의 점수를 얻습니다.
네 주사위를 굴렸을 때 나온 숫자가 정수 매개변수 a, b, c, d로 주어질 때, 얻는 점수를 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

my_string: "cvsgiorszzzmrpaqpe"
index_list: [16, 6, 5, 3, 12, 14, 11, 11, 17, 12, 7]
result: "programmers"

예제 1번의 my_string에서 인덱스 3, 5, 6, 11, 12, 14, 16, 17에 해당하는 글자는 각각 g, o, r, m, r, a, p, e이므로 my_string에서 index_list에 들어있는 원소에 해당하는 인덱스의 글자들은 각각 순서대로 p, r, o, g, r, a, m, m, e, r, s입니다. 따라서 "programmers"를 return 합니다.

| #   | a   | b   | c   | d   | result |
| --- | --- | --- | --- | --- | ------ |
| 1   | 2   | 2   | 2   | 2   | 2222   |
| 2   | 4   | 1   | 4   | 4   | 1681   |
| 3   | 6   | 3   | 3   | 6   | 27     |
| 4   | 2   | 5   | 2   | 6   | 30     |
| 5   | 6   | 4   | 2   | 5   | 2      |

1번에서 네 주사위 숫자가 모두 2로 같으므로 1111 × 2 = 2222점을 얻습니다. 따라서 2222를 return 합니다.

2번에서 세 주사위에서 나온 숫자가 4로 같고 나머지 다른 주사위에서 나온 숫자가 1이므로 (10 × 4 + 1)2 = 412 = 1681점을 얻습니다. 따라서 1681을 return 합니다.

3번에서 a, d는 6으로, b, c는 3으로 각각 같으므로 (6 + 3) × |6 - 3| = 9 × 3 = 27점을 얻습니다. 따라서 27을 return 합니다.

4번에서 두 주사위에서 2가 나오고 나머지 다른 두 주사위에서 각각 5, 6이 나왔으므로 5 × 6 = 30점을 얻습니다. 따라서 30을 return 합니다.

5번에서 네 주사위 숫자가 모두 다르고 나온 숫자 중 가장 작은 숫자가 2이므로 2점을 얻습니다. 따라서 2를 return 합니다.

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int a, int b, int c, int d) {
        int answer = 0;

        if(a == b && b == c && c == d){
            answer = saveAnswer(a,a,a,0);
        }

        if(a == b && b == c && a != d){
            answer = saveAnswer(a,d,a,1);
        } else if(a == b && b == d && a != c){
            answer = saveAnswer(a,c,a,1);
        } else if(a == c && c == d && a != b){
            answer = saveAnswer(a,b,a,1);
        } else if(b == c && c == d && b != a){
            answer = saveAnswer(b,a,a,1);
        }

        if(a == b && a != c && c == d){
            answer = saveAnswer(a,c,a,2);
        } else if(a == c && a != b && b == d){
            answer = saveAnswer(a,b,a,2);
        } else if(a == d && a != b && b == c){
            answer = saveAnswer(a,b,a,2);
        }

        if(a == b && a != c && a != d && c != d){
            answer = saveAnswer(a,c,d,3);
        } else if(a == c && a != b && a != d && b != d){
            answer = saveAnswer(a,b,d,3);
        } else if(a == d && a != b && a != c && b != c){
            answer = saveAnswer(a,b,c,3);
        } else if(b == c && b != a && b != d && a != d){
            answer = saveAnswer(a,a,d,3);
        } else if(b == d && b != a && b != c && a != c){
            answer = saveAnswer(a,a,c,3);
        } else if(c == d && c != a && c != b && a != b){
            answer = saveAnswer(a,a,b,3);
        }

        if(a != b && b != c && c != d && a != c && a != d && b != d){
            if(a < b && a < c && a < d){
                answer = a;
            } else if(b < c && b < d){
                answer = b;
            } else if(c < d){
                answer = c;
            } else {
                answer = d;
            }
        }
        return answer;
    }
    private int saveAnswer(int p, int q, int r, int cases){
        int result = 0;
        if(cases == 0){
            result = 1111 * p;
        } else if(cases == 1){
            result = (int)Math.pow(10 * p + q, 2);
        } else if(cases == 2){
            result = (p + q) * Math.abs(p - q);
        } else if(cases == 3){
            result = q * r;
        }
        return result;
    }
}
```

##### 풀이 설명

saveAnswer 함수를 만들어 각 케이스에 따른 유동적인 값을 도출할 수 있도록 하였습니다. 이후 문제의 조건에 따라 해당 함수에 인자 값을 넣고 cases의 값에 따라 제어하게 로직을 구성했습니다.

저 같은 경우는 모든 케이스에 대한 대응을 하는 것으로 해당 문제를 풀었습니다만..사실 더 좋은 방법이 있습니다.
바로 주사위 수에 대해 크기 순으로 정렬하여 문제를 푸는 것입니다. 정렬하여 푼 풀이를 먼저 소개해드리고 리뷰를 이어가겠습니다.

#### 주사위 수에 대해 크기 순으로 정렬하여 풀기

```java
import java.util.Arrays;

class Solution {
    public int solution(int a, int b, int c, int d) {

        int[] dice = { a, b, c, d };
        Arrays.sort(dice);

        int ans = 0;

        if (dice[0] == dice[3]) {
            ans = 1111 * dice[3];
        } else if (dice[0] == dice[2] || dice[1] == dice[3]) {
            ans = (int) Math.pow(dice[1] * 10 + (dice[0] + dice[3] - dice[1]), 2);
        } else if (dice[0] == dice[1] && dice[2] == dice[3]) {
            ans = (dice[0] + dice[3]) * (dice[3] - dice[0]);
        } else if (dice[0] == dice[1]) {
            ans = dice[2] * dice[3];
        } else if (dice[1] == dice[2]) {
            ans = dice[0] * dice[3];
        } else if (dice[2] == dice[3]) {
            ans = dice[0] * dice[1];
        } else {
            ans = dice[0];
        }

        return ans;
    }
}
```

dice라는 int[]을 선언하고 그 안에 주사위 값들을 넣어 Arrays.sort로 dice 요소의 값을 정렬해줍니다.
이후 로직에 맞게 코드를 작성합니다. 보면 저의 풀이에 비해 조건문의 수가 적은 것을 확인할 수 있습니다.
저 같은 경우 정렬하지 않았기 때문에 모든 a,b,c,d의 값을 비교하여 케이스를 분류하였는데 정렬이 되었다면 모든 주사위 값을 비교할 필요가 없어지기 때문에 간결해졌으며, 가독성이 좋아졌습니다.

#### 결론

앞으로 특정 조건에 따라 값을 분류해야 하고 어떤 값이 들어올지 모르는 상황에선 정렬하고 문제에 접근하면 훨씬 가독성 좋은 코드를 작성할 수 있다.
