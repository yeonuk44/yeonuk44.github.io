---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Server_Authentication
title: About server authentication
# title: About server authentication
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Development
# multiple tag entries are possible
tags: [development]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-04-12 09:00:00 +0900
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

## 서비스 공격과 대응 방법에 대하여 알아본 글입니다.

안녕하세요!

오늘은 서비스 공격과 대응 방법에 대해 알아보고자 합니다.

글을 본격적으로 시작하기에 앞서,

**---오늘의 TMI---**

오늘은 국회의원 선거일입니다! 어머님 덕분에 놓치지 않고 시간 내서 다녀왔네요ㅎㅎ 취업을 준비하다 보니 시간표에만 집중하게 되게 날짜는 잘 안 보게 되는 것 같아요ㅎㅎ 투표를 통해 기여하는 느낌이 들어 기분 좋은 하루입니다. 오늘도 모두 힘내세요!

**---TMI 끝---**

글로 돌아가겠습니다!

서비스 공격은 악의적인 공격자가 네트워크 또는 시스템에 대해 공격을 시도하여 정상적인 서비스 제공을 방해하는 행위를 의미합니다.

이제 서비스 공격의 주요 유형들에 대해 하나씩 알아보도록 하겠습니다.

{:data-align="center"}

<!-- outline-end -->

### 죽음의 핑 (Ping of Death)

죽음의 핑은 공격자가 과도한 크기의 ICMP (Internet Control Message Protocol) 패킷을 전송하여 대상 시스템을 다운시키는 공격입니다.

이러한 ICMP 패킷은 시스템이 처리하기 어려운 크기로 조작되어 과부하를 유발시킵니다.

### 스머핑 (Smurfing)

스머핑은 공격자가 네트워크 상의 브로드캐스트 주소로 ICMP Echo Request 메시지를 보내 대량의 응답을 유도하여 대상 시스템을 공격하는 방법입니다.

이를 통해 대상 시스템의 대역폭을 소모하고 서비스를 마비시킬 수 있습니다.

### SYN Flooding

SYN Flooding은 공격자가 대상 시스템에 대해 대량의 TCP 연결 요청 (SYN 패킷)을 보내 응답을 기다리지 않고 연결을 종료하는 공격입니다.

이로 인해 대상 시스템의 자원이 고갈되어 정상적인 서비스를 제공할 수 없게 됩니다.

### Land Attack

Land Attack은 공격자가 송신 IP 주소와 목적지 IP 주소를 동일하게 설정하여 대상 시스템에 대한 TCP 패킷을 지속적으로 전송하는 공격입니다.

이러한 패킷은 시스템에 의해 자기 자신으로 인식되어 무한 루프에 빠지게 만들어 서비스를 마비시킵니다.

### DDoS (Distributed Denial of Service)

DDoS는 여러 대의 컴퓨터 또는 장치들을 조작하여 대상 시스템에 대한 공격을 동시에 수행하는 공격입니다.

이를 통해 대상 시스템의 자원이 고갈되어 서비스를 마비시킵니다.

### 피싱 (Phishing)

피싱은 공격자가 가짜 웹사이트나 이메일을 통해 사용자의 개인 정보를 탈취하는 공격입니다.

공격자는 사회 공학적 기법을 사용하여 사용자를 속여 개인 정보를 노출시키게 합니다.

### Ping Flood

Ping Flood는 공격자가 대량의 ICMP Echo Request 메시지를 대상 시스템으로 전송하는 공격입니다.

이로 인해 대상 시스템의 자원이 고갈되어 서비스를 마비시킵니다.

### 스위치 재잼 (Switch Jamming)

스위치 재잼은 공격자가 네트워크 스위치를 공격하여 스위치의 동작을 방해하고 네트워크 트래픽을 마비시키는 공격입니다.

이로 인해 네트워크 연결이 중단되어 서비스를 제공할 수 없게 됩니다.

### 블루프린팅 (Bluesnarfing)

블루프린팅은 공격자가 블루투스를 통해 다른 기기에 불법적으로 접근하여 개인 정보를 탈취하는 공격입니다.

공격자는 블루투스 연결을 통해 기기에 대한 완전한 제어권을 획득할 수 있습니다.

### 웜 (Worm)

웜은 자체 실행이 가능하며 네트워크를 통해 자동으로 전파되는 악성 소프트웨어입니다.

웜은 대상 시스템에 대한 공격을 수행하거나 시스템의 자원을 고갈시키는 등의 행위를 할 수 있습니다.

### 키로거 공격 (Keylogger Attack)

키로거 공격은 공격자가 대상 시스템에 키로거 소프트웨어를 설치하여 사용자의 키보드 입력을 모니터링하고 탈취하는 공격입니다.

이를 통해 사용자의 비밀번호나 개인 정보를 알아낼 수 있습니다.

### 랜섬웨어 (Ransomware)

랜섬웨어는 공격자가 대상 시스템에 악성 소프트웨어를 침투시켜 파일을 암호화하고 복원을 위해 금전적 보상을 요구하는 공격입니다.

이로 인해 사용자는 파일에 대한 접근을 잃게 됩니다.

### 백도어 (Backdoor)

백도어는 공격자가 대상 시스템에 악성 소프트웨어나 보안 취약점을 이용하여 비인가된 접근을 허용하는 통로를 만드는 공격입니다.

이를 통해 공격자는 시스템에 대한 완전한 제어권을 획득할 수 있습니다.

## 마치며

이상으로 오늘은 서비스 공격 유형에 대해 간략히 알아보았습니다.

이러한 공격으로부터 시스템과 네트워크를 보호하기 위해서는 방화벽, 침입 탐지 시스템 및 보안 업데이트와 같은 보안 대책을 강화하는 것이 중요합니다.

또한 사용자들은 신뢰할 수 있는 소스에서의 파일 다운로드와 링크 클릭에 주의해야 합니다.

안전한 온라인 환경을 위해 보안에 대한 지속적인 관심과 주의가 필요합니다.

감사합니다.
