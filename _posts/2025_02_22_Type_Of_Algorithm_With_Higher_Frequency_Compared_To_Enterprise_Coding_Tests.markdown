---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_Type_Of_Algorithm_With_Higher_Frequency_Compared_To_Enterprise_Coding_Tests
title: Type of algorithm with higher frequency compared to enterprise coding tests
# title: Type of algorithm with higher frequency compared to enterprise coding tests
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Development
# multiple tag entries are possible
tags: [development, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2025-02-22 09:00:00 +0900
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

## 기업 코딩테스트 대비 빈도 수 높은 알고리즘 유형에 대하여 알아본 글입니다.

오랜만에 인사드립니다. 개인적 사정으로 글 작성을 미루게 되었는데 마음을 다잡고 다시 작성해볼까 합니다!

다시 코딩테스트를 준비하기 위해 오늘은 자주 출제되는 빈도 수 높은 알고리즘 유형을 알아보았습니다.

{:data-align="center"}

<!-- outline-end -->

1. 최적화(greedy) 알고리즘
   - 문제의 접근 방법에 따라 반복문 재귀 백트래킹의 방법으로 풀어야하는 유형 존재합니다.
2. 누적합(Prefix sum) 알고리즘
   - 정수론을 사용하는 방법이 있고, DP(탑다운, 바텀업), 메모이제이션 등으로 풀어야하는 유형이 존재 누적합 유형은 '점화식'을 구상하는 방법으로 바텀업 DP 유형의 문제가 존재합니다.
3. 완전탐색
   - 가장 보편적으로 많이 나오는 코테 유형, 문제의 접근 방법에 따라 반복문 재귀 백트래킹 방법으로 푸는 유형 존재합니다.
4. 2차원 DP
   - 2차원 동적 계획법(Dynamic Programming)은 문제를 2차원 배열 형태로 정의하고, 작은 문제들을 해결하여 전체 문제를 해결하는 유형으로 문자열 비교나 LIS/LCS 등 문제에서도 사용됩니다. 배열 dp[i][j]를 이용해서 부분 문제의 최적 해를 저장하며, 이전 셀들의 값을 이용해 현재 셀의 값을 계산합니다.
5. LIS, LCS
   - LIS는 최장 증가 부분 수열로 원소 n개인 배열의 일부 원소를 골라내 만든 부분 수열 중, 각 원소가 이전 원소보다 크다는 조건을 만족하고, 그 길이가 최대인 부분 수열을 찾는 방법입니다.
   - LCS는 두 개 이상의 수열이나 문자열 중 공통된 원소를 가지고 있고, 길이가 가장 긴 부분 수열/문자열을 의미합니다.
6. 투포인터
   - 두 개의 포인터를 사용해 배열이나 리스트를 탐색하는 기법으로 시작점과 끝점을 서렁해 조건에 맞게 포인터를 이동시키며 문제를 해결합니다. 주로 정렬된 배열에서 특정 합을 찾거나, 연속 부분 배열의 합을 구하는 문제에 사용됩니다.
7. 이분탐색
   - 정렬된 배열에서 특정 값을 찾는 알고리즘으로 배열의 중간 요소와 찾고자 하는 값을 비교해 탐색 범위를 절반으로 줄여나갑니다. 반복적 또는 재귀적으로 수행되며, 시간 복작도는 O(log n)입니다. 주로 숫자 탐색, 조건을 만족하는 최대/최소값 찾기 등에 사용됩니다.
8. DFS / BFS
   - 그래프 탐색 알고리즘으로 DFS는 한 경로를 끝까지 탐색 후 돌아와 다른 경로를 탐색하며, 재귀나 스택을 사용합니다.BFS는 시작 노드에서 가까운 노드부터 탐색하며, 큐를 사용합니다. DFS는 주로 경로 탐색, 미로 찾기에 사용되고, BFS는 최단 거리 찾기, 레벨별 탐색에 유용합니다.
9. 다익스트라
   - 가중치가 있는 그래프에서 한 정점에서 다른 모든 정점으로 최단 경로를 찾는 알고리즘입니다. 우선순위 큐를 사용해 방문하지 않은 정점 중 가장 짧은 경로를 선택하고, 인접한 정점의 경로를 갱신합니다. 주로 네트워크 경로 최적화, 지도 애플리케이션 등에 사용됩니다.
10. 트리
    - 계층적 구조를 가진 데이터를 효율적으로 탐색하고 처리하는 데 사용됩니다. 대표적으로 이진 트리, 이진 탐색 트리, AVL 트리, 트라이 등이 있습니다. 주로 순회(전위, 중위, 후위), 삽입, 삭제, 검색 등의 유형에 해당합니다.
