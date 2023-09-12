---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Check_Suffix_Implementation
title: About the Check Suffix Implementation (with.Java)
# title: About the Check Suffix Implementation (with.Java)

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
date: 2023-09-12 09:00:00 +0900
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

### 문자열 여러 번 뒤집기 구현에 대하여(with.Java) 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

문자열 my_string과 이차원 정수 배열 queries가 매개변수로 주어집니다.

queries의 원소는 [s, e] 형태로, my_string의 인덱스 s부터 인덱스 e까지를 뒤집으라는 의미입니다.

my_string에 queries의 명령을 순서대로 처리한 후의 문자열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

my_string: "rermgorpsam"

queries: [[2, 3], [0, 7], [5, 9], [6, 10]]

result: "programmers"

my_string은 "rermgorpsam"이고 주어진 queries를 순서대로 처리하면 다음과 같습니다.

| queries | my_string     |
| ------- | ------------- |
| [2, 3]  | "remrgorpsam" |
| [0, 7]  | "progrmersam" |
| [5, 9]  | "prograsremm" |
| [6, 10] | "programmers" |

따라서 "programmers"를 return 합니다.

<!-- | i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     | -->

#### 문제에 대한 나의 풀이

```java
import java.util.*;

class Solution {
    public String solution(String my_string, int[][] queries) {
        StringBuilder answer = new StringBuilder();
        ArrayList<Character> arr = new ArrayList<Character>();

        for(int k = 0; k < my_string.length(); k++) {
            arr.add(my_string.charAt(k));
        }

        for(int i = 0; i < queries.length; i++) {
            int startIndex = queries[i][0];
            int endIndex = queries[i][1];
            reverse(arr, startIndex, endIndex);
        }

        for (int l = 0; l < arr.size(); l++) {
            answer.append(arr.get(l));
        }

        return answer.toString();
    }

    private void reverse(ArrayList<Character> arr, int startIndex, int endIndex) {
        while (startIndex < endIndex) {
            char temp = arr.get(startIndex);
            arr.set(startIndex, arr.get(endIndex));
            arr.set(endIndex, temp);
            startIndex++;
            endIndex--;
        }
    }
}
```

##### 풀이 설명

StringBuilder를 통해 문자열 합성을 위한 변수 answer를 선언합니다.

이후 Character 타입으로 제어하기 위한 arr를 선언해준 뒤, my_string을 char 형식으로 문자 하나 씩 arr에 저장해줍니다.

이후 reverse(arr, startIndex, endIndex); 3개의 인자를 넘겨주고 reverse 함수를 실행시킵니다.

reverse 함수는 startIndex가 endIndex보다 작을 때 계속해서 배열의 순서대로 값을 삽입합니다. 마지막과 시작 값을 변경해주기 위해선 가변적이지 않는 변수가 필요합니다.

이 때 가변하지 않는 변수 temp를 선언해줘 start값을 미리 할당해주고 endIndex에 해당 값을 삽입해줍니다.

연산을 계속 수행하기 위해 startIndex 1 씩 증가, endIndex를 1씩 감소 시켜줍니다.

이는 반복문의 실행 수를 절반으로 줄이기 위해 한 번에 수행합니다. 이후 answer에 arr의 요소를 삽입한 뒤, 출력합니다.

저와 비슷한 로직이지만 깨달음을 주는 코드가 있어 리뷰해보고자 합니다.

#### 또 다른 풀이

```java
class Solution {

    char[] arr;

    public String solution(String my_string, int[][] queries) {

        arr = my_string.toCharArray();

        for (int[] query : queries) {
            reverse(query[0], query[1]);
        }

        return new String(arr);
    }

    private void reverse(int s, int e) {
        while (s < e) {
            char temp = arr[s];
            arr[s++] = arr[e];
            arr[e--] = temp;
        }
    }
}
```

##### 풀이 설명

해당 코드는 저의 코드와 로직이 거의 비슷합니다. 눈 여겨 볼 부분은 reverse 함수의 파라미터에 arr가 없다는 점과 void, 배열 속 index에 증감연산자 입니다.

하나 씩 풀이해보겠습니다. 우선 reverse 함수의 파라미터에 arr가 없습니다. 그럼에도 왜 다른 함수에서 사용할 수 있을까요? 해당 코드에서 **arr는 클래스 Solution의 인스턴스 변수입니다.** 이러한 인스턴스 변수는 클래스 내의 모든 인스턴스 메서드에서 접근할 수 있으며, 따라서 reverse 메서드에서도 arr에 직접 접근할 수 있습니다.

인스턴스 변수는 객체가 생성될 때마다 새로운 복사본이 만들어지며, 해당 객체의 모든 인스턴스 메서드에서 동일한 변수를 참조합니다. 따라서 reverse 메서드에서 arr의 내용을 변경하면, 그 변경 사항은 solution 메서드에서도 그대로 반영됩니다.

이러한 특성 때문에, 별도로 arr를 파라미터로 전달하지 않아도 reverse 메서드 내에서 arr에 접근하고 수정할 수 있습니다. 이는 객체 지향 프로그래밍에서 자주 사용되는 패턴 중 하나로, 클래스 내의 메서드들이 동일한 상태를 공유하고 조작할 수 있게 해줍니다.

다음은 void입니다. Java에서 void 키워드는 특정 메서드가 반환값을 갖지 않을 때 사용됩니다. 즉, 메서드가 작업을 수행하지만 호출자에게 값을 반환하지 않을 경우, 메서드 선언에서 반환 타입으로 void를 지정합니다.

void를 사용하는 메서드는 주로 어떤 작업을 수행하거나 객체의 상태를 변경하며, 그 **결과를 호출자에게 반환할 필요가 없는 경우에 사용됩니다.**

마지막으로 배열 속 index 자리에 있는 증감연산자입니다. 대체로 저희는 증감 연산자를 밖으로 빼서 사용하는데 이처럼 index 자리에 증감연산자를 넣는 경우는 흔히 보기 힘들었습니다. 그래서 조금 알아보았습니다.

++x: 먼저 피연산자의 값을 1 증가시킨 후에 해당 연산을 진행함.

x++: 먼저 해당 연산을 수행하고 나서, 피연산자의 값을 1 증가시킴.

--x: 먼저 피연산자의 값을 1 감소시킨 후에 해당 연산을 진행함.

x--: 먼저 해당 연산을 수행하고 나서, 피연산자의 값을 1 감소시킴.

즉, 배열 속에서도 해당 연산이 가능하다는 점을 알고 넘어가면 좋을 것 같아 포함하였습니다. 고생하셨습니다.

###### 참고

**StringBuilder 란?**

StringBuilder는 Java에서 문자열을 효율적으로 조작할 수 있는 클래스입니다. 일반 문자열 연결 연산은 불변 객체인 String을 사용하기 때문에 많은 연결 연산이 필요할 경우 성능에 불리할 수 있습니다.

기존 문자열 연결 방식은 새 문자열을 추가할 때마다 새로운 String 객체를 생성하므로, 많은 연결이 필요한 경우 상당한 오버헤드가 발생할 수 있습니다.

반면 StringBuilder는 내부 버퍼를 사용해 문자열을 조작하므로 문자열 연결을 더 빠르게 수행할 수 있습니다. StringBuilder를 사용하면 문자열 조작 작업에서 시간 복잡도와 공간 복잡도가 크게 향상될 수 있습니다.
