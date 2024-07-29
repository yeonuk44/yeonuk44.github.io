---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Cluster_Analysis
title: 군집분석에 대하여
# title: About Cluster Analysis
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Statistics
# multiple tag entries are possible
tags: [statistics]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-07-29 09:00:00 +0900
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

## 군집분석에 대하여 알아본 글입니다.

안녕하세요!

오늘은 군집분석에 대하여 알아보겠습니다.

분류 모델의 성능을 평가하기 위한 여러 가지 지표가 있습니다.

{:data-align="center"}

<!-- outline-end -->

### 정확도 (Accuracy)

정확도는 전체 예측 중 올바르게 예측한 비율을 나타내며, (TP + TN) / (TP + TN + FP + FN)으로 계산됩니다.

이는 모델이 올바르게 예측한 샘플의 비율을 나타냅니다. 하지만 불균형한 클래스 분포에서는 적절한 지표가 아닐 수 있습니다.

### 정밀도 (Precision)과 재현율 (Recall)

정밀도는 모델이 Positive로 예측한 것 중에서 실제로 Positive인 비율을 나타내며, TP / (TP + FP)으로 계산됩니다.

재현율은 실제로 Positive인 것 중에서 모델이 Positive로 예측한 비율을 나타내며, TP / (TP + FN)으로 계산됩니다.

정밀도는 거짓 긍정을 줄이는 데 초점을 두고, 재현율은 거짓 부정을 줄이는 데 초점을 둡니다.

### F1 점수 (F1 Score)

F1 점수는 정밀도와 재현율의 조화 평균으로, 2 _ (정밀도 _ 재현율) / (정밀도 + 재현율)로 계산됩니다.

이는 정밀도와 재현율이 균형을 이루고 있는지를 나타내는 지표입니다.

### ROC 곡선과 AUC

#### ROC(Receiver Operating Characteristic) 곡선

모델의 분류 성능을 나타내는 그래프로, 재현율에 대한 거짓 긍정 비율(FPR)의 곡선을 나타냅니다.

#### AUC(Area Under the Curve)

ROC 곡선 아래의 면적으로, 모델의 성능을 종합적으로 평가하는 지표입니다.

### 혼동 행렬 (Confusion Matrix)

이원 분류에서 실제 클래스와 모델의 예측값을 표로 나타낸 것으로, TP, TN, FP, FN을 나타내어 모델의 분류 성능을 상세하게 평가하는 데 사용됩니다.

### 활용

이러한 평가 지표들은 모델의 성능을 종합적으로 평가하고, 모델의 각각의 성능을 이해하는 데 활용됩니다.

### 마치며

분류 모델의 평가 지표를 종합적으로 고려하여 모델의 성능을 정확하게 평가하고, 모델의 성능을 개선하는 데 활용됩니다.

감사합니다!
