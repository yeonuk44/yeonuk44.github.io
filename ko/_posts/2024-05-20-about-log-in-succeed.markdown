---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Log_In_Succeed
title: 로그인 성공? (with. Java)
# title: log-in succeed? (with Java)
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
date: 2024-05-20 09:00:00 +0900
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

## "로그인 성공? (with. Java)" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이는 프로그래머스에 로그인하려고 합니다.

머쓱이가 입력한 아이디와 패스워드가 담긴 배열 id_pw와 회원들의 정보가 담긴 2차원 배열 db가 주어질 때, 다음과 같이 로그인 성공, 실패에 따른 메시지를 return하도록 solution 함수를 완성해주세요.

아이디와 비밀번호가 모두 일치하는 회원정보가 있으면 "login"을 return합니다.

로그인이 실패했을 때 아이디가 일치하는 회원이 없다면 “fail”를, 아이디는 일치하지만 비밀번호가 일치하는 회원이 없다면 “wrong pw”를 return 합니다.

#### 제한사항

- 회원들의 아이디는 문자열입니다.
- 회원들의 아이디는 알파벳 소문자와 숫자로만 이루어져 있습니다.
- 회원들의 패스워드는 숫자로 구성된 문자열입니다.
- 회원들의 비밀번호는 같을 수 있지만 아이디는 같을 수 없습니다.
- id_pw의 길이는 2입니다.
- id_pw와 db의 원소는 [아이디, 패스워드] 형태입니다.
- 1 ≤ 아이디의 길이 ≤ 15
- 1 ≤ 비밀번호의 길이 ≤ 6
- 1 ≤ db의 길이 ≤ 10
- db의 원소의 길이는 2입니다.

#### 입출력 예시

<!-- | lines                     | result |
| ------------------------- | ------ |
| [[0, 1], [2, 5], [3, 9]]  | 2      |
| [[-1, 1], [1, 3], [3, 9]] | 0      |
| [[0, 5], [3, 9], [1, 10]] | 8      | -->

| id_pw                     | db                                                                              | result     |
| ------------------------- | ------------------------------------------------------------------------------- | ---------- |
| ["meosseugi", "1234"]     | [["rardss", "123"], ["yyoom", "1234"], ["meosseugi", "1234"]]                   | "login"    |
| ["programmer01", "15789"] | [["programmer02", "111111"], ["programmer00", "134"], ["programmer01", "1145"]] | "wrong pw" |
| ["rabbit04", "98761"]     | [["jaja11", "98761"], ["krong0313", "29440"], ["rabbit00", "111333"]]           | "fail"     |

### 문제에 대한 나의 풀이

```java
class Solution {
    public String solution(String[] id_pw, String[][] db) {
        String answer = "";
        for(int i = 0; i < db.length; i++){
            if(id_pw[0].equals(db[i][0]) && id_pw[1].equals(db[i][1])){
                return "login";
            }else if(id_pw[0].equals(db[i][0])){
                return "wrong pw";
            }else{
                answer = "fail";
            }
        }
        return answer;
    }
}
```

### 풀이 리뷰

입력된 아이디와 비밀번호를 나타내는 id_pw 배열과 데이터베이스 정보를 나타내는 db 이차원 배열이 주어집니다.

루프를 사용하여 데이터베이스의 각 행을 반복합니다.

각 반복에서 아이디와 비밀번호를 확인하여 로그인 상태를 결정합니다.

만약 아이디와 비밀번호가 모두 일치하면 "login"을 반환하고 함수를 종료합니다.

아이디는 일치하지만 비밀번호가 일치하지 않으면 "wrong pw"를 반환하고 함수를 종료합니다.

login과 wrong pw를 바로 반환하고 함수를 종료하는 까닭은 문제에 두 가지 케이스의 경우 바로 리턴하라고 명시되어 있기 때문입니다. (문제를 잘 읽어봐야 합니다.)

모든 행을 확인한 후에도 일치하는 정보가 없으면 "fail"을 반환합니다.

함수가 종료될 때까지 일치하는 정보가 없으면 "fail"이 반환됩니다.
