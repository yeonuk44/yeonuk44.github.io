---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Joystick
title: Joystick (with.Java)
# title: Joystick (with.Java)
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
date: 2024-08-14 09:00:00 +0900
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

## 조이스틱 (with.Java) 문제에 대하여 알아본 글입니다.

코딩 테스트 문제를 풀며, 풀었던 문제에 대한 회고를 해보고자 합니다.

문제에 대해 먼저 알아보겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 문제

점심시간에 도둑이 들어, 일부 학생이 체육복을 도난당했습니다.

다행히 여벌 체육복이 있는 학생이 이들에게 체육복을 빌려주려 합니다.

학생들의 번호는 체격 순으로 매겨져 있어, 바로 앞번호의 학생이나 바로 뒷번호의 학생에게만 체육복을 빌려줄 수 있습니다.

예를 들어, 4번 학생은 3번 학생이나 5번 학생에게만 체육복을 빌려줄 수 있습니다.

    체육복이 없으면 수업을 들을 수 없기 때문에 체육복을 적절히 빌려 최대한 많은 학생이 체육수업을 들어야 합니다.

전체 학생의 수 n, 체육복을 도난당한 학생들의 번호가 담긴 배열 lost, 여벌의 체육복을 가져온 학생들의 번호가 담긴 배열 reserve가 매개변수로 주어질 때, 체육수업을 들을 수 있는 학생의 최댓값을 return 하도록 solution 함수를 작성해주세요.

#### 제한사항

- 전체 학생의 수는 2명 이상 30명 이하입니다.
- 체육복을 도난당한 학생의 수는 1명 이상 n명 이하이고 중복되는 번호는 없습니다.
- 여벌의 체육복을 가져온 학생의 수는 1명 이상 n명 이하이고 중복되는 번호는 없습니다.
- 여벌 체육복이 있는 학생만 다른 학생에게 체육복을 빌려줄 수 있습니다.
- 여벌 체육복을 가져온 학생이 체육복을 도난당했을 수 있습니다. 이때 이 학생은 체육복을 하나만 도난당했다고 가정하며, 남은 체육복이 하나이기에 다른 학생에게는 체육복을 빌려줄 수 없습니다.

#### 입출력 예시

| n   | lost   | reserve   | return |
| --- | ------ | --------- | ------ |
| 5   | [2, 4] | [1, 3, 5] | 5      |
| 5   | [2, 4] | [3]       | 4      |
| 3   | [3]    | [1]       | 2      |

### 문제에 대한 나의 풀이

```java
import java.util.Arrays;

class Solution {
    public int solution(int n, int[] lost, int[] reserve) {
        int answer = 0;
        Arrays.sort(reserve);
        Arrays.sort(lost);

        answer = n - lost.length;

        for (int i = 0; i < lost.length; i++) {
			for (int j = 0; j < reserve.length; j++) {
				if (lost[i] == reserve[j]) {
					answer++;
					lost[i] = -1;
					reserve[j] = -1;
                    break;
				}
			}
		}
        for(int num : lost){
            for (int j = 0; j < reserve.length; j++) {
				if (num - 1 == reserve[j] || num + 1 == reserve[j]) {
					answer++;
					reserve[j] = -1;
					break;
				}
			}
        }

        return answer;
    }
}
```

### 풀이 설명

먼저 여분의 체육복을 가져온 학생들과 도난당한 학생들의 배열을 정렬합니다.

이는 이후 비교 과정에서 더 효율적으로 진행하기 위함입니다.

도난당한 학생 수를 제외한 전체 학생 수를 초기값으로 설정합니다.

여분의 체육복을 가져온 학생이 도난당한 학생에게 체육복을 빌려줄 수 있는 경우를 고려하여 일단 도난당한 학생 수를 전체 학생 수에서 뺍니다.

도난당한 학생과 여분의 체육복을 가져온 학생이 같은 번호인 경우를 찾아서 해당 학생들을 처리합니다.

도난당한 학생이 체육복을 잃어버렸지만 여분의 체육복을 가져온 경우이므로, 이 학생들은 체육 수업을 들을 수 있습니다.

이 때, 해당 학생들을 도난당한 학생 수를 제외한 전체 학생 수에 더해줍니다.

처리된 학생들은 다음 탐색에서 중복하여 고려되지 않도록 해당 학생들의 번호를 -1로 변경합니다.

여분의 체육복을 가져온 학생들과 도난당한 학생들 사이의 거리가 1인 경우를 고려하여 체육복을 빌려줄 수 있는지를 탐색합니다.

여분의 체육복을 가져온 학생들과 도난당한 학생들 사이의 거리가 1이면 서로 체육복을 빌려줄 수 있습니다.

이 경우, 도난당한 학생 수를 제외한 전체 학생 수에 더해줍니다.

처리된 학생들은 다음 탐색에서 중복하여 고려되지 않도록 해당 학생들의 번호를 -1로 변경합니다.

최종적으로 도난당한 학생을 제외한 전체 학생 수가 체육 수업을 들을 수 있는 학생 수입니다. 이 값을 반환합니다.

이 코드는 두 번의 반복문을 통해 주어진 조건에 따라 학생들이 체육 수업을 들을 수 있는 경우를 탐색하고, 그 수를 반환합니다.

### 결론

위 코드에는 여러 조건에 따라 도난당한 학생과 여분의 체육복을 가져온 학생 사이의 관계를 탐색하는 과정이 구현되어 있습니다.

이 과정은 주어진 문제의 조건에 맞게 상세히 설계되었으며, 먼저 도난당한 학생과 여분의 체육복을 가져온 학생이 같은 번호인 경우를 처리하고, 그 다음으로는 여분의 체육복을 가져온 학생들과 도난당한 학생들 사이의 거리가 1인 경우를 고려하여 체육복을 빌려줄 수 있는지를 확인합니다.
