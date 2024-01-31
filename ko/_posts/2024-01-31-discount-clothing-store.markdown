---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Discount_Clothing_Store
title: 옷가게 할인 받기(with.Java)
# title: Get a discount at a clothing store (with.Java)

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
date: 2024-01-31 09:00:00 +0900
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

## "옷가게 할인 받기" 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고와 다른 풀이 방법을 알아보며, 알아가고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

머쓱이네 옷가게는 10만 원 이상 사면 5%, 30만 원 이상 사면 10%, 50만 원 이상 사면 20%를 할인해줍니다.
구매한 옷의 가격 price가 주어질 때, 지불해야 할 금액을 return 하도록 solution 함수를 완성해보세요.

#### 제한사항

10 ≤ price ≤ 1,000,000
price는 10원 단위로(1의 자리가 0) 주어집니다.
소수점 이하를 버린 정수를 return합니다.

#### 입출력 예시

| price   | result  |
| ------- | ------- |
| 150,000 | 142,500 |
| 580,000 | 464,000 |

<!-- | start_num | end_num | result |
| --------- | ------- | ------ |
| 10        | 3       | 0      | -->

### 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int price) {
        int discount = 0;
        if (price >= 500000) {
            discount = price / 5;
        } else if (price >= 300000) {
            discount = price / 10;
        } else if (price >= 100000) {
            discount = price / 20;
        }
        System.out.println(price - discount);
        return price - discount;
    }
}
```

### 풀이 설명

int discount = 0;: 할인액을 저장할 변수 discount를 초기화합니다.

if (price >= 500000) : 입력 가격 price가 500,000 이상인 경우:

discount = price / 5;: 가격의 20% 할인을 계산합니다.

else if (price >= 300000) : 입력 가격 price가 300,000 이상이고 500,000 미만인 경우:

discount = price / 10;: 가격의 10% 할인을 계산합니다.

else if (price >= 100000) : 입력 가격 price가 100,000 이상이고 300,000 미만인 경우:

discount = price / 20;: 가격의 5% 할인을 계산합니다.

System.out.println(price - discount);: 할인된 가격을 출력합니다.

return price - discount;: 할인된 가격을 반환합니다.

### 변경된 제한 사항에 대한 풀이

만약 소수점 이하를 버린 정수를 return하는 것이 아닌 소수점 이하를 반올림한다면 1원 단위까지 계산한다면 어떻게 풀이하면 될까요?

#### 변경된 제한 사항 문제에 대한 나의 풀이

```java
class Solution {
    public int solution(int price) {
        int discount = 0;
        if (price >= 500000) {
            discount = (int) Math.ceil(price * 0.2);
        } else if (price >= 300000) {
            discount = (int) Math.ceil(price * 0.1);
        } else if (price >= 100000) {
            discount = (int) Math.ceil(price * 0.05);
        }
        return price - discount;
    }
}
```

#### 변경된 제한 사항 문제 풀이

int discount = 0;: 할인액을 저장할 변수 discount를 초기화합니다.

if (price >= 500000) : 입력 가격 price가 500,000 이상인 경우:

discount = (int) Math.ceil(price \* 0.2);: 가격의 20% 할인을 계산하고, Math.ceil 함수를 사용하여 올림 처리합니다.

else if (price >= 300000) : 입력 가격 price가 300,000 이상이고 500,000 미만인 경우:

discount = (int) Math.ceil(price \* 0.1);: 가격의 10% 할인을 계산하고, Math.ceil 함수를 사용하여 올림 처리합니다.

else if (price >= 100000) : 입력 가격 price가 100,000 이상이고 300,000 미만인 경우:

discount = (int) Math.ceil(price \* 0.05);: 가격의 5% 할인을 계산하고, Math.ceil 함수를 사용하여 올림 처리합니다.

return price - discount;: 할인된 가격을 계산하고 반환합니다.
