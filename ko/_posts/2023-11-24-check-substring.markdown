---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Check_Substring
title: 부분 문자열인지 확인하기(with.Java)
# title: Check if it's a substring (with.Java)
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
date: 2023-11-24 09:00:00 +0900
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

### "배열의 원소 삭제하기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

정수 배열 arr과 delete_list가 있습니다.

arr의 원소 중 delete_list의 원소를 모두 삭제하고 남은 원소들은 기존의 arr에 있던 순서를 유지한 배열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| arr                       | delete_list                 | result                 |
| ------------------------- | --------------------------- | ---------------------- |
| [293, 1000, 395, 678, 94] | [94, 777, 104, 1000, 1, 12] | [293, 395, 678]        |
| [110, 66, 439, 785, 1]    | [377, 823, 119, 43]         | [110, 66, 439, 785, 1] |

#### 문제에 대한 나의 풀이

```java
import java.util.ArrayList;
class Solution {
    public int[] solution(int[] arr, int[] delete_list) {
        ArrayList<Integer> arrList = new ArrayList<Integer>();
        int count = 0;
        for(int ele1: arr){
            for(int ele2: delete_list){
                if(ele1 == ele2){
                    count++;
                }
            }
            if(count == 0){
                arrList.add(ele1);
            }
            count = 0;
        }
        int[] answer = new int[arrList.size()];
        for(int i = 0; i < arrList.size(); i++){
            answer[i] = arrList.get(i);
        }
        return answer;
    }
}
```

##### 풀이 설명

ArrayList<Integer> arrList = new ArrayList<Integer>();: 정수를 저장할 ArrayList arrList를 생성합니다. 이 리스트는 삭제할 요소를 제외한 나머지 요소들을 저장할 용도로 사용됩니다.

int count = 0;: 삭제할 요소와 일치하는 요소의 수를 저장하는 변수 count를 초기화합니다.

for(int ele1 : arr) : 입력 배열 arr을 반복하면서 각 요소를 검사합니다.

for(int ele2 : delete_list) : 삭제할 목록 delete_list를 반복하면서 각 요소를 검사합니다.

if(ele1 == ele2) : 현재 ele1과 ele2가 일치하는 경우:

count를 증가시킵니다.
if(count == 0) : count가 0인 경우 (즉, ele1이 delete_list에 없는 경우):

arrList에 ele1을 추가합니다.
count = 0;: count를 초기화하여 다음 ele1 요소를 검사할 준비를 합니다.

int[] answer = new int[arrList.size()];: arrList의 크기와 동일한 크기를 가진 배열 answer를 생성합니다.

for(int i = 0; i < arrList.size(); i++) : arrList의 요소들을 배열 answer에 복사합니다.

return answer;: 삭제할 목록 delete_list에 포함되지 않은 요소들로 이루어진 배열 answer를 반환합니다.

이 코드는 입력 배열 arr에서 삭제할 목록 delete_list에 포함되지 않은 요소들을 모아서 새로운 배열을 생성하고 반환합니다.
