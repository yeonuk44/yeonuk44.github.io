---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Carpet
title: Carpet (with.Java)
# title: Carpet (with.Java)
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
date: 2024-08-09 09:00:00 +0900
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

## 카펫 (with.Java) 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고를 해보고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

Leo는 카펫을 사러 갔다가 아래 그림과 같이 중앙에는 노란색으로 칠해져 있고 테두리 1줄은 갈색으로 칠해져 있는 격자 모양 카펫을 봤습니다.

Leo는 집으로 돌아와서 아까 본 카펫의 노란색과 갈색으로 색칠된 격자의 개수는 기억했지만, 전체 카펫의 크기는 기억하지 못했습니다.

Leo가 본 카펫에서 갈색 격자의 수 brown, 노란색 격자의 수 yellow가 매개변수로 주어질 때 카펫의 가로, 세로 크기를 순서대로 배열에 담아 return 하도록 solution 함수를 작성해주세요.

#### 제한사항

- 갈색 격자의 수 brown은 8 이상 5,000 이하인 자연수입니다.
- 노란색 격자의 수 yellow는 1 이상 2,000,000 이하인 자연수입니다.
- 카펫의 가로 길이는 세로 길이와 같거나, 세로 길이보다 깁니다.

#### 입출력 예시

| brown | yellow | return |
| ----- | ------ | ------ |
| 10    | 2      | [4, 3] |
| 8     | 1      | [3, 3] |
| 24    | 24     | [8, 6] |

### 문제에 대한 나의 풀이

```java
makeCase(numArr, cnt+1, size, idxArr, visit);
                visit[i] = false;
            }
        }
    }

    private boolean isPrime(int n){
        if(n < 2) return false;
        for(int i = 2; i <= Math.sqrt(n); i++)
            if(n % i == 0) return false;
        return true;
    }
}
```

### 풀이 설명

- solution 메서드는 문자열 numbers를 입력으로 받습니다.
- numbers를 문자 배열로 변환하여 각 숫자를 쪼갭니다.
- 각 숫자로 가능한 모든 조합을 생성하기 위해 makeCase 메서드를 호출합니다.
- makeCase 메서드는 재귀적으로 호출되며, 백트래킹을 사용하여 가능한 모든 조합을 생성합니다.
- makeCase 메서드 내에서는 현재까지 선택된 인덱스를 저장하는 배열 idxArr과 해당 인덱스가 방문되었는지를 나타내는 배열 visit를 사용합니다.
- 각 조합이 완성된 후에는 해당 숫자가 소수인지 판별하여 numSet에 추가합니다.
- isPrime 메서드는 주어진 숫자가 소수인지를 판별합니다.
- 모든 조합 생성이 완료된 후에는 numSet의 크기를 반환하여 소수의 개수를 구합니다.

### 결론

이 코드는 백트래킹을 사용하여 주어진 숫자로 가능한 모든 조합을 생성하고, 그 중에서 소수인 숫자의 개수를 반환하는 문제를 해결합니다.
