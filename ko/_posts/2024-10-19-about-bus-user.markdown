---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Bus_User
title: 2019 카카오 개발자 겨울 인턴십 문제, 불량 사용자(with.Java)
# title: 2019 Kakao Developer Winter Internship Problem, Bad User (with.Java)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test, dfs]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-10-19 09:00:00 +0900
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

## 2019 카카오 개발자 겨울 인턴십 문제, 불량 사용자(with.Java) 에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

개발팀 내에서 이벤트 개발을 담당하고 있는 "무지"는 최근 진행된 카카오이모티콘 이벤트에 비정상적인 방법으로 당첨을 시도한 응모자들을 발견하였습니다.

이런 응모자들을 따로 모아 불량 사용자라는 이름으로 목록을 만들어서 당첨 처리 시 제외하도록 이벤트 당첨자 담당자인 "프로도" 에게 전달하려고 합니다.

이 때 개인정보 보호을 위해 사용자 아이디 중 일부 문자를 `'*'` 문자로 가려서 전달했습니다.

가리고자 하는 문자 하나에 `'*'` 문자 하나를 사용하였고 아이디 당 최소 하나 이상의 `'*'` 문자를 사용하였습니다.

"무지"와 "프로도"는 불량 사용자 목록에 매핑된 응모자 아이디를 제재 아이디 라고 부르기로 하였습니다.

예를 들어, 이벤트에 응모한 전체 사용자 아이디 목록이 다음과 같다면

응모자 아이디

- frodo
- fradi
- crodo
- abc123
- frodoc

다음과 같이 불량 사용자 아이디 목록이 전달된 경우,

불량 사용자

- fr*d*
- abc1\*\*
- 불량 사용자에 매핑되어 당첨에서 제외되어야 야 할 제재 아이디 목록은 다음과 같이 두 가지 경우가 있을 수 있습니다.

제재 아이디

- frodo
- abc123
- 제재 아이디
- fradi
- abc123

이벤트 응모자 아이디 목록이 담긴 배열 user_id와 불량 사용자 아이디 목록이 담긴 배열 banned_id가 매개변수로 주어질 때, 당첨에서 제외되어야 할 제재 아이디 목록은 몇가지 경우의 수가 가능한 지 return 하도록 solution 함수를 완성해주세요.

#### 제한사항

- user_id 배열의 크기는 1 이상 8 이하입니다.
- user_id 배열 각 원소들의 값은 길이가 1 이상 8 이하인 문자열입니다.
- 응모한 사용자 아이디들은 서로 중복되지 않습니다.
- 응모한 사용자 아이디는 알파벳 소문자와 숫자로만으로 구성되어 있습니다.
- banned_id 배열의 크기는 1 이상 user_id 배열의 크기 이하입니다.
- banned_id 배열 각 원소들의 값은 길이가 1 이상 8 이하인 문자열입니다.
- 불량 사용자 아이디는 알파벳 소문자와 숫자, 가리기 위한 문자 '\*' 로만 이루어져 있습니다.
- 불량 사용자 아이디는 '\*' 문자를 하나 이상 포함하고 있습니다.
- 불량 사용자 아이디 하나는 응모자 아이디 중 하나에 해당하고 같은 응모자 아이디가 중복해서 제재 아이디 목록에 들어가는 경우는 없습니다.
- 제재 아이디 목록들을 구했을 때 아이디들이 나열된 순서와 관계없이 아이디 목록의 내용이 동일하다면 같은 것으로 처리하여 하나로 세면 됩니다.

#### 입출력 예

| user_id                                         | banned_id                              | result |
| ----------------------------------------------- | -------------------------------------- | ------ |
| ["frodo", "fradi", "crodo", "abc123", "frodoc"] | ["fr*d*", "abc1**"]                    | 2      |
| ["frodo", "fradi", "crodo", "abc123", "frodoc"] | ["*rodo", "*rodo", "******"]           | 2      |
| ["frodo", "fradi", "crodo", "abc123", "frodoc"] | ["fr*d*", "*rodo", "******", "******"] | 3      |

<!-- | begin | target | words                                      | return |
| ----- | ------ | ------------------------------------------ | ------ |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log", "cog"] | 4      |
| "hit" | "cog"  | ["hot", "dot", "dog", "lot", "log"]        | 0      | -->

### 문제 풀이

```java
import java.util.HashSet;
class Solution {
    HashSet<HashSet<String>> large_storage = new HashSet<>();
    HashSet<String> small_storage = new HashSet<>();

    public int solution(String[] user_id, String[] banned_id) {

        explor(0, small_storage, user_id, banned_id);

        return large_storage.size();
    }

    public void explor(int len, HashSet<String> small_storage, String[] user, String[] ban_user){
        if(ban_user.length == len){
            large_storage.add(new HashSet<>(small_storage));
        }else{
            for(int i = 0; i < user.length; i++){
                if(small_storage.contains(user[i])){
                    continue;
                }

                if(filter(user[i], ban_user[len])){
                    small_storage.add(user[i]);
                    explor(len + 1, small_storage, user, ban_user);
                    small_storage.remove(user[i]);
                }
            }
        }
    }
    public boolean filter(String user_str, String ban_user_str){
        boolean result = true;
        if(user_str.length() != ban_user_str.length()){
            return false;
        }
        for(int i = 0; i < user_str.length(); i++){
            if(ban_user_str.charAt(i) != '*' && user_str.charAt(i) != ban_user_str.charAt(i)){
                result = false;
                break;
            }
        }
        return result;
    }
}
```

#### 풀이 설명

제재 아이디 목록을 찾는 문제는 재귀와 해시셋을 활용하여 해결할 수 있습니다.

이 문제에서는 제재 목록을 중복 없이 저장하고, 모든 가능한 조합을 찾아내는 것이 목표입니다.

먼저, 클래스 변수로 두 개의 해시셋을 정의합니다.

large_storage는 최종 제재 목록들을 저장하기 위한 큰 저장소입니다.

small_storage는 현재 탐색 중인 제재 목록을 저장하는 임시 저장소입니다.

solution 메서드는 사용자 아이디와 제재 아이디 배열을 입력으로 받아 제재 목록의 개수를 반환합니다.

이 메서드는 재귀 함수 explor를 호출하여 탐색을 시작합니다.

explor 메서드는 현재 탐색 깊이 len과 임시 저장소 small_storage, 사용자 아이디 배열 user, 제재 아이디 배열 ban_user를 매개변수로 받습니다.

탐색 깊이가 제재 아이디 배열의 길이와 같아지면, 현재 임시 저장소의 복사본을 큰 저장소에 추가합니다.

그렇지 않으면 사용자 아이디 배열을 순회하며, 이미 임시 저장소에 포함된 아이디는 건너뛰고, 필터를 통과하는 아이디를 임시 저장소에 추가한 후 재귀 호출을 진행합니다.

재귀 호출이 끝나면 현재 아이디를 임시 저장소에서 제거하여 상태를 복원합니다.

filter 메서드는 주어진 사용자 아이디와 제재 아이디를 비교하여 필터 조건을 만족하는지 확인합니다.

먼저 두 문자열의 길이가 다르면 false를 반환합니다.

이후 각 문자를 비교하여, 제재 아이디에 \*가 아닌 문자가 있고, 해당 문자가 사용자 아이디의 동일 위치 문자와 다르면 false를 반환합니다.

모든 조건을 만족하면 true를 반환합니다.

이 접근 방식은 효율적으로 제재 목록을 탐색하고 저장할 수 있습니다.

HashSet을 사용하여 중복을 제거하고, 재귀 호출을 통해 모든 가능한 조합을 찾아냅니다.

특히, new HashSet<>(small_storage)를 사용하여 현재 임시 저장소의 복사본을 만들어 재귀 호출 시 독립적인 상태를 유지하도록 합니다.

이를 통해 문제에서 요구하는 제재 목록의 개수를 정확히 계산할 수 있습니다

풀이를 하며 알게된 점이 있어 공유하고자 합니다.

처음 풀이한 코드

```java
import java.util.HashSet;

class Solution {
    HashSet<HashSet<String>> large_storage = new HashSet<>();
    String[] user;
    String[] ban_user;

    public int solution(String[] user_id, String[] banned_id) {
        user = user_id;
        ban_user = banned_id;
        HashSet<String> small_storage = new HashSet<>();

        explor(0, small_storage);

        return large_storage.size();
    }

    public void explor(int len, HashSet<String> small_storage){
        if(ban_user.length == len){
            large_storage.add(small_storage);
            return;
        }

        for(int i = 0; i < user.length; i++){
            if(small_storage.contains(user[i])){
                continue;
            }

            if(filter(user[i], ban_user[len])){
                small_storage.add(user[i]);
                explor(len + 1, small_storage);
                small_storage.clear();
            }
        }
    }
    public boolean filter(String user_str, String ban_user_str){
        boolean result = true;
        if(user_str.length() != ban_user_str.length()){
            return false;
        }
        for(int i = 0; i < user_str.length(); i++){
            if(ban_user_str.charAt(i) != '*' && user_str.charAt(i) != ban_user_str.charAt(i)){
                result = false;
                break;
            }
        }
        return result;
    }
}
```

해당 코드는 통과하지 못했습니다. 그 이유는 2가지였습니다.

1. HashSet의 특성 때문에 발생하는 문제

explor 함수에서 작은 저장소(small_storage)에 사용자 ID를 추가하고, 재귀 호출 후 다시 작은 저장소를 초기화(clear())하는 부분이 문제입니다.

HashSet을 clear하게 되면 현재 재귀 호출이 끝나기 전에 이미 저장된 상태의 HashSet이 사라져버리게 됩니다.

HashSet은 참조형이기 때문에 clear()를 호출하면 모든 참조하는 곳에서도 데이터가 사라집니다.

2. HashSet을 복사하지 않음

small_storage를 직접 재귀 호출에 넘기고, clear를 호출하면서 전체 저장소가 초기화되는 문제가 있습니다.

new HashSet<>(small_storage)와 같이 새로 복사된 HashSet을 재귀 호출에 넘겨야 합니다.

자세히 알아보겠습니다!

HashSet의 특성과 재귀 호출에서의 상태 관리 문제를 해결하는 것이 핵심이었습니다.

- HashSet의 특성
  HashSet은 자바의 컬렉션 프레임워크 중 하나로, 중복을 허용하지 않는 데이터를 저장할 때 사용합니다.

중요한 점은, HashSet은 참조 타입이기 때문에 다른 변수에 할당하거나 메서드 인자로 전달할 때 그 자체를 복사하지 않고, 동일한 객체에 대한 참조를 전달한다는 점입니다.

- 문제의 원인
  기존 코드에서 small_storage를 재귀 함수 explor에 전달하고, 내부에서 small_storage.clear()를 호출함으로써 발생한 문제가 있었습니다.

clear()를 호출하면 small_storage가 참조하는 모든 곳에서 데이터가 제거되기 때문에, 재귀 호출이 끝나기 전에 이미 저장된 상태가 사라지게 됩니다.

- 해결 방법
  각 재귀 호출이 독립적인 상태를 가지도록 하기 위해 new HashSet<>(small_storage)를 사용하여 small_storage의 복사본을 만들어 재귀 호출에 전달했습니다.

이렇게 하면 각 재귀 호출은 자신만의 HashSet을 가지게 되며, 다른 호출에 영향을 미치지 않습니다.

##### 결론

복사본 사용: new HashSet<>(small_storage)를 사용하여 small_storage의 현재 상태를 복사하여 재귀 호출에 전달합니다. 이렇게 하면 각 재귀 호출이 독립적인 HashSet을 가지게 되어 다른 호출에 영향을 미치지 않습니다.
원래 상태로 복구: 재귀 호출이 끝나면 small_storage.remove(user[i])를 호출하여 small_storage를 이전 상태로 되돌립니다. 이렇게 하면 상위 호출에서 small_storage가 올바른 상태를 유지할 수 있습니다.
감사합니다!
