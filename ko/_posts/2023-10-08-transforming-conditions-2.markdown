---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Transforming_conditions_2
title: 조건에 맞게 수열 변환하기 2(with.Java)
# title: Transforming a sequence based on conditions 2 (with.Java)

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
date: 2023-10-08 09:00:00 +0900
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

### 조건에 맞게 수열 변환하기에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 배열 arr가 주어집니다.

arr의 각 원소에 대해 값이 50보다 크거나 같은 짝수라면 2로 나누고, 50보다 작은 홀수라면 2를 곱하고 다시 1을 더합니다.

이러한 작업을 x번 반복한 결과인 배열을 arr(x)라고 표현했을 때, arr(x) = arr(x + 1)인 x가 항상 존재합니다.

이러한 x 중 가장 작은 값을 return 하는 solution 함수를 완성해 주세요.

단, 두 배열에 대한 "="는 두 배열의 크기가 서로 같으며, 같은 인덱스의 원소가 각각 서로 같음을 의미합니다.

##### 입출력 예시

| arr                    | result |
| ---------------------- | ------ |
| [1, 2, 3, 100, 99, 98] | 5      |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

#### 문제에 대한 나의 풀이

```java
import java.util.*;
class Solution {
    public int solution(int[] arr) {
        int answer = 0;
        int[] tempArr = new int[arr.length];
        do {
            for(int i = 0; i < arr.length; i++){
            tempArr[i] = arr[i];
            }
            for(int i = 0; i < arr.length; i++){
                if(arr[i] >= 50 && arr[i] % 2 == 0){
                    arr[i] = arr[i] / 2;
                } else if(arr[i] < 50 && arr[i] % 2 != 0){
                    arr[i] = arr[i] * 2 + 1;
                }
            }
            answer++;
        } while(!Arrays.equals(tempArr, arr));
        return answer - 1;
    }
}
```

##### 풀이 설명

answer 변수는 변환 과정이 반복되는 횟수를 저장합니다.

tempArr 배열은 현재의 arr 배열 값을 복사하기 위한 임시 배열입니다.

do-while 루프는 tempArr와 arr 배열이 같지 않을 때까지 실행됩니다.

첫 번째 for 루프에서는 현재 arr 배열의 값을 tempArr 배열로 복사합니다.

두 번째 for 루프에서는 각 요소에 대한 조건에 따라 연산을 수행하여 arr 배열을 변경합니다.

answer를 증가시킴으로써 반복 횟수를 기록합니다.

Arrays.equals(tempArr, arr)는 tempArr와 arr 배열이 같은지 비교합니다. 서로 같지 않으면 루프가 계속됩니다.

루프가 종료되면 변환된 횟수인 answer - 1을 반환합니다.

코드를 작성하며 배열의 참조를 조심해야겠다는 생각을 했습니다.

###### 배열 복사 시 주의할 점

**예시**

```java
 int[] intArray1 = new int[] { 1, 2, 3 };
  int[] intArray2 = new int[] { 1, 2, 3 };

if(intArray1 == intArray2) {
    System.out.println("두 배열은 동일합니다.");
  } else {
    System.out.println("두 배열은 동일하지 않습니다.");
  }
}

// return: 두 배열은 동일하지 않습니다.
```

**왜 그럴까요?**

이유는 Java에서 배열은 객체로 간주되며 배열 변수는 배열 객체를 가리키는 참조(reference)입니다.

따라서 == 연산자를 사용하여 배열 변수를 비교할 때, 실제로는 참조 주소(reference address)를 비교하게 됩니다.

이는 자바의 모든 객체에 적용되는 규칙입니다. 따라서 배열의 내용이 동일하더라도 서로 다른 메모리 위치에 있는 배열은 == 연산자로 비교했을 때 항상 동일하지 않다고 판단됩니다.

이러한 동작은 자바의 객체 비교 규칙으로 인해 발생하며, 배열 뿐만 아니라 모든 객체에 적용됩니다.

객체의 내용이 동일한지 비교하려면 Arrays.equals() 메서드나 직접 배열의 요소를 비교하는 방법을 사용해야 합니다.

다른 언어에서도 대부분 비슷한 동작을 하지만, 언어에 따라 이러한 동작이 미묘하게 다를 수 있을 수도 있습니다.

그러나 객체의 비교는 대부분 참조 주소를 기반으로 하므로 일반적인 원칙은 유사할 것입니다. 돌아와 결론은 참조 타입의 변수의 값은 Heap 영역의 객체 주소이기 때문에 요소의 값이 아닌 주소 값을 비교하는 것이 되어 다르다고 결과를 반환합니다.

이는 배열 뿐만 아니라 객체를 비교하는 문자열 등의 타입에도 적용됩니다.
