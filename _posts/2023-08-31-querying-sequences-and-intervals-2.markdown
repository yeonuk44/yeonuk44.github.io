---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Querying_Sequences_and_Intervals_2
title: Querying Sequences and Intervals 2(with.Java)
# title: Querying Sequences and Intervals 2(with.Java)
# implementing arrays for given conditions

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
date: 2023-08-31 09:00:00 +0900
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

### Querying Sequences and Intervals 2(with.Java)

{:data-align="center"}

<!-- outline-end -->

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.
문제에 대해 먼저 알아보겠습니다.

#### 문제

정수 배열 arr가 주어집니다. arr를 이용해 새로운 배열 stk를 만드려고 합니다.

변수 i를 만들어 초기값을 0으로 설정한 후 i가 arr의 길이보다 작으면 다음 작업을 반복합니다.

만약 stk가 빈 배열이라면 arr[i]를 stk에 추가하고 i에 1을 더합니다.
stk에 원소가 있고, stk의 마지막 원소가 arr[i]보다 작으면 arr[i]를 stk의 뒤에 추가하고 i에 1을 더합니다.
stk에 원소가 있는데 stk의 마지막 원소가 arr[i]보다 크거나 같으면 stk의 마지막 원소를 stk에서 제거합니다.
위 작업을 마친 후 만들어진 stk를 return 하는 solution 함수를 완성해 주세요.

##### 입출력 예시

arr: [1, 4, 2, 5, 3]
result: [1, 2, 3]

각 작업을 마친 후에 배열의 변화를 나타내면 다음 표와 같습니다.

| i   | arr[i] | stk     |
| --- | ------ | ------- |
| 0   | 1      | []      |
| 1   | 4      | [1]     |
| 2   | 2      | [1,4]   |
| 2   | 2      | [1]     |
| 3   | 5      | [1,2]   |
| 4   | 3      | [1,2,5] |
| 4   | 3      | [1,2]   |
| -   | -      | [1,2,3] |

따라서 [1, 2, 3]을 return 합니다.

#### 문제에 대한 나의 풀이

```java
import java.util.*;

class Solution {
    public int[] solution(int[] arr) {
        ArrayList<Integer> temp = new ArrayList<Integer>();
        for(int i = 0; i < arr.length; i++){
            if(temp.isEmpty()){
                temp.add(arr[i]);
                continue;
            }
            while(temp.get(temp.size()-1) >= arr[i]){
                temp.remove(temp.size()-1);
                if(temp.isEmpty()){
                    temp.add(arr[i]);
                    break;
                }
            }
            if(temp.get(temp.size()-1) < arr[i]){
                temp.add(arr[i]);
                continue;
            }
        }
        int[] answer = new int[temp.size()];
        for(int j = 0; j < temp.size(); j++){
            answer[j] = temp.get(j);
        }
        return answer;
    }
}
```

##### 풀이 설명

제가 작성한 코드는 모든 코드가 그렇듯 실행 순서를 고려하지 않을 수 없었습니다. 조건 중 "stk에 원소가 있는데 stk의 마지막 원소가 arr[i]보다 크거나 같으면 stk의 마지막 원소를 stk에서 제거합니다."라는 조건이 있었는데 해당 조건을 충족시키기 위해선 특정 입출력 테스트 케이스를 생각해보면 계속 배열의 요소를 삭제해주고, 계속 배열 속 요소를 비워내면 결국 빈 배열에 arr의 요소를 추가해줘야 하기 때문입니다.

코드에 대한 설명을 이어가겠습니다. isEmpty() 함수를 통해 빈배열에 대해 add(arr[i])로 요소를 추가해줍니다. 이후 조건에 따라 다음 index로 넘어가야하기에 continue를 사용했습니다.
다음은 고민이 있었던 요소 삭제에 대한 부분입니다. 문제에선 요소를 추가하는 조건이 선 기술되어 있었으나 실행 순서를 고려하여 해당 조건을 선구현하게 되었습니다. 설명드리자면 while문을 통해 temp의 마지막 요소에 대해 arr[i]의 값이 크거나 같을 시, remove()함수를 통해 해당 요소를 삭제해줬습니다. 단순히 삭제만 하게 되면 특정한 테스트 케이스에 따라 배열의 사이즈가 부족한 현상이 생길 수 있습니다. 계속 마지막 요소를 삭제하니 빈배열이 되고 음수의 index를 가진 ArrayList가 될 수 있기 때문입니다. 이해를 돕기 위해 간단히 다른 테스트 케이스에 비교하면 arr 값이 [2, 3, 4, 2, 1]이면 문제의 조건에 따라 return은 [1]이 됩니다. 해당 케이스의 경우 index의 흐름에 따라 i=0 [2], i=1 [2,3], i=2 [2,3,4], i=3 [2,3], [2], [],[2] i=4 [],[1] 결국 [1]을 반환합니다. 흐름을 참고하시면 알 수 있듯 특수한 테스트 케이스의 경우 빈배열이 만들어지고 이는 size를 통해 마지막요소를 체킹할 경우 배열의 크기가 문제가 될 수 있으며, 빈배열이 되었을 때 마지막 요소를 추가할 경우 arr[i] = 1, 비교하는 요소도 [1]일 경우 while 등 반복문에서 무한 루프에 빠질 수 있습니다.

결론은 단순하게 제거하는 로직 이후에 요소를 추가하는 요소하느 것으로는 예외처리를 하지 않았다고 볼 수 있습니다. 따라서 빈배열이 되어 발생하는 케이스를 방지하기 위해 빈배열일 경우 요소를 추가하고 while문을 강제로 빠져나가고 break문을 사용하였습니다. 다음 코드는 제거해야 하는 조건을 만족시키지 않을 경우 즉, 결과가 저장된 배열의 마지막 요소가 arr[i] 작을 경우 해당 요소를 추가하고 그렇지 않으면 continue로 반복문을 순회하도록 로직을 짰습니다. 해당 문제는 저에게 간단하게 접근했다가 많은 테스트 케이스에서 예외처리에 대한 고민이 필요했던 문제였습니다.
