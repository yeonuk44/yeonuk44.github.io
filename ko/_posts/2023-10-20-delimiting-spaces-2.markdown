---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Delimiting_Spaces_2
title: 공백으로 구분하기 2(with.Java)
# title: Delimiting Spaces 2 (with.Java)
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
date: 2023-10-20 09:00:00 +0900
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

### 공백으로 구분하기 2에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

#### 문제

단어가 공백 한 개 이상으로 구분되어 있는 문자열 my_string이 매개변수로 주어질 때, my_string에 나온 단어를 앞에서부터 순서대로 담은 문자열 배열을 return 하는 solution 함수를 작성해 주세요.

##### 입출력 예시

| my_string       | result               |
| --------------- | -------------------- |
| " i love you"   | ["i", "love", "you"] |
| " programmers " | ["programmers"]      |

예제 1번의 my_string은 " i love you"로 공백을 기준으로 단어를 나누면 "i", "love", "you" 3개의 단어가 있습니다.

따라서 ["i", "love", "you"]를 return 합니다.

예제 2번의 my_string은 " programmers "로 단어는 "programmers" 하나만 있습니다.

따라서 ["programmers"]를 return 합니다.

#### 문제에 대한 나의 풀이

```java
import java.util.*;

class Solution {
    public String[] solution(String my_string) {
        String[] answer = my_string.split(" ");
        List<String> list = new ArrayList<>(Arrays.asList(answer));
        list.removeAll(Arrays.asList(""));
        return list.toArray(new String[0]);
    }
}

```

##### 풀이 설명

public String[] solution(String my_string): 문자열 my_string을 입력으로 받아 문제를 해결하는 함수입니다. 반환값으로 문자열 배열을 반환합니다.

String[] answer = my_string.split(" ");: 주어진 문자열 my_string을 공백을 기준으로 분리하여 단어들을 담은 문자열 배열 answer를 생성하는 코드입니다.

List<String> list = new ArrayList<>(Arrays.asList(answer));: 위에서 생성한 배열 answer를 리스트로 변환하여 list 변수에 저장합니다. 이를 통해 리스트를 조작하고 요소를 추가/제거할 수 있도록 준비합니다.

list.removeAll(Arrays.asList(""));: 빈 문자열을 리스트에서 모두 제거하는 코드입니다. Arrays.asList("")를 사용하여 빈 문자열을 담은 리스트를 생성하고, 이 리스트에 속한 모든 요소들을 리스트 list에서 제거합니다.

return list.toArray(new String[0]);: 리스트 list에 저장된 요소들을 String 배열로 변환하여 반환하는 코드입니다. 여기서 new String[0]는 크기가 0인 새로운 String 배열을 생성하는 역할을 합니다. 이 배열에 리스트 list에 저장된 요소들이 복사되어 담기게 됩니다.

결과적으로, 이 코드는 주어진 문자열 my_string을 공백을 기준으로 분리하여 빈 문자열을 제거한 뒤, 남은 단어들을 문자열 배열로 반환하는 작업을 수행합니다.

코드를 작성하며, 배열의 초기 크기를 0으로 지정하면 배열에 요소가 삽입되지 않을거라고 생각했는데 의도대로 동작하였습니다.

알게된 것도 첨부하겠습니다.

배열의 초기 크기를 0으로 지정하더라도 코드가 의도한 대로 작동하는 이유는 Java의 배열과 관련된 동작 방식 때문입니다.

배열의 크기가 0으로 지정되었다고 해서 실제로 배열이 아예 생성되지 않는 것이 아니라, 크기 0의 배열 객체가 생성되는 것입니다.

이 배열 객체는 실제 요소를 저장할 수 있는 공간은 가지고 있지 않지만, 배열 객체 자체는 존재하게 됩니다.

Java에서 배열은 고정된 크기를 가지므로, 배열의 크기를 생성할 때 지정해줘야 합니다.

그래서 new String[0]는 크기가 0인 배열 객체를 생성하는 것이며, 이 배열 객체는 요소를 저장할 공간은 없지만 배열 객체 자체는 생성됩니다.

그리고 list.toArray(new String[0]) 코드는 이 배열 객체에 요소들을 담아서 반환하는데, 이때 요소들이 들어갈 수 있는 새로운 배열이 필요하다는 신호를 줍니다.

Java 내부에서 이 배열 객체를 새로운 크기로 복사하여 요소를 채워 넣게 됩니다.

따라서 초기 크기가 0인 배열 객체를 생성하더라도, list.toArray(new String[0]) 코드를 통해 요소를 담아 반환하는 과정에서 실제로는 크기가 조정된 새로운 배열이 생성되어 요소들이 채워지게 됩니다.
