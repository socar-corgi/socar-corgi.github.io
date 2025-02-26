---
layout: post
title:  "신입 백엔드 개발자의 우당탕탕 엔지니어링 온보딩팀 교육 후기"
subtitle: 온보딩 강의부터 Dogfooding 프로젝트까지
date: 2022-10-17 09:00:00 +0900
category: dev
background : "/img/onboarding-service-engineering/0_background.jpg"
author: corgi
comments: true
tags:
    - backend
    - frontend
    - developer
    - service-engineering
    - onboarding
---

<style scoped>
    thead {
    font-size: 15px;
    }
    tbody {
    font-size: 13px;
    }
</style>

안녕하세요! 올해 3월부로 쏘카 백엔드 엔지니어로 합류한 코기(이해원)입니다. 

쏘카 서비스 엔지니어링(Service Engineering) 본부에 입사하면 엔지니어링 온보딩 팀으로 소속되어 온보딩 과정을 밟게 됩니다. 입사 후 받은 온보딩 교육이 저를 지금의 모습으로 성장시켜주는데 가장 큰 도움이 되었다고 생각합니다. 
그 이유를 크게 **세 가지**로 함축해 봤습니다.

- 쏘카에서 사용 중인 `Kotlin, Spring Boot, AWS` 와 같은 언어 / 기술과 `Datadog, BuddyWorks, ArgoCD, Rancher` 등 여러 개발 도구에 대해 교육받고 실습하며 학습할 기회를 제공받았습니다.
- 실제로 상용화하는 프로젝트를 동기끼리 0(Zero)부터 시작해서 만들어보고 이에 대한 피드백을 받으며 학습하고 성장할 수 있었습니다.
- 서비스 엔지니어링 본부의 동료들과 친해지고 쏘카에 더욱 빠르게 적응할 수 있었습니다.

**쏘카에서 온보딩 교육을 어떻게 진행**하는지, 또 **온보딩 교육을 통해 무엇을 배우고 얼마나 더 성장할 수 있었는지** 알리고자 이 글을 작성하게 되었습니다. 
아래에 해당하신다면 이 글을 끝까지 읽어주시면 좋습니다.
- 쏘카의 엔지니어링 온보딩 과정이 궁금하신 분 
- 소프트웨어 엔지니어를 준비하고 계신 분
- 쏘카의 기술 문화가 궁금하신 분
- 동료들과 함께 학습하며 기술적인 성장을 해나가고 싶은 분

<br />

---
## 목차

1. [서비스 엔지니어링 본부와 엔지니어링 온보딩 팀이란?](#1-서비스-엔지니어링-본부와-엔지니어링-온보딩-팀이란)
2. [온보딩 강의](#2-온보딩-강의)  
    2.1. [프로그래머의 기본 & 쏘카의 Service Architecture](#21-프로그래머의-기본--쏘카의-service-architecture)  
    2.2. [BackEnd 강의 & 쏘카의 개발 문화](#22-backend-강의--쏘카의-개발-문화)  
    2.3. [FrontEnd 강의 & 쏘카의 Infra와 DB](#23-frontend-강의--쏘카의-infra와-db)  
3. [Dogfooding Project](#3-dogfooding-project)  
    3.1. [Dogfooding 이란?](#31-dogfooding이란)  
    3.2. [Kick-off 미팅](#32-kick-off-미팅)  
    3.3. [프로젝트 진행](#33-프로젝트-진행)  
    3.4. [스프린트 데모](#34-스프린트-데모)  
    3.5. [회고 및 플래닝](#35-회고-및-플래닝)  
4. [동료와의 교류 및 스터디](#4-동료와의-교류-및-스터디)  
    4.1. [서비스 엔지니어링 본부 타운홀 미팅 자기소개](#41-서비스-엔지니어링-본부-타운홀미팅-자기소개)  
    4.2. [쏘풍데이](#42-쏘풍-데이)  
    4.3. [스터디](#43-스터디)  
5. [온보딩 졸업 후 각자 버킷으로](#5-온보딩-졸업-후-각자-버킷으로)
6. [나날이 발전하는 온보딩 교육](#6-나날이-발전하는-온보딩-교육)
7. [나에게 온보딩 교육이란?](#7-나에게-온보딩-교육이란)
8.  [마치며](#8-마치며)

<br />

---
## 1. 서비스 엔지니어링 본부와 엔지니어링 온보딩 팀이란?

쏘카의 서비스 엔지니어링(Service Engineering) 본부는 **‘쏘카를 이용하는 고객들에게 더 나은 가치를 제공하기 위해 새로운 서비스를 만들고 기존 서비스들을 안정적으로 운영하는 모든 것을 개발하고 책임진다.’**라는 미션 아래 쏘카 서비스와 관련된 소프트웨어를 전반적으로 담당하는 조직입니다.

서비스 엔지니어링 본부는 **‘버킷'** 을 활용하여 서비스(또는 도메인) 단위로 쪼개서 `MSA(MicroService Architecture)`를 추진하고 있습니다. 기본적으로 BackEnd, FrontEnd 등 직군 별로 팀이 있고 그 팀원들이 도메인별로 각자 다른 버킷에 포함되어 버킷 내 서비스를 담당하고 있습니다. 이에 더해 비슷한 버킷을 그룹 단위로 묶어 그룹 별 리더가 총괄하는 구조로 운영되고 있습니다.

버킷의 업무는 빠르게 변화하는 시장에 대응하기 위해 **MVP 완성을 목표로 하는 스프린트 방식으로 진행**됩니다. 각 버킷 별로 차이가 있을 수 있지만 보통 2주 또는 3주 내외입니다.

현재 신규 사업 또는 서비스의 확장에 힘을 실어주기 위해 버킷이 계속해서 만들어지고 있습니다. 게시글 작성 시점을 기준으로 운영되는 11개의 버킷은 다음과 같습니다.

| <center>버킷명</center>    | <center>업무</center>             |
| :------------------------- |:--------------------------------|
| Core Platform Bucket       | 예약 및 성능 개선                      |
| Car Sharing Bucket(B2C)    | 카셰어링 서비스(왕복, 존편도, 부름, 페어링)      |
| Core Experience Bucket     | 쏘카 앱/웹(Android/iOS, Web)        |
| Accounts Bucket            | 회원 관련(가입, 탈퇴, 로그인, 휴면, 인증 등)    |
| Payment Bucket             | 결제 / 정산 / 크레딧                   |
| Operation Framework Bucket | 백오피스                            |
| Asset Bucket               | 운영 시스템(사고 관리, 전 관리) / 차량 자원관리자  |
| Marketing Bucket           | 패스포트 / 마케팅(이벤트, 알림, 쿠폰, 타게팅)    |
| B2B Bucket                 | 쏘카 비즈니스(웹, 멤버십, 플랜)             |
| FMS Bucket                 | FMS(차량 관제 시스템)                  |
| 유레카 Bucket              | 쏘카 통합 차량관리 서비스(세차 관리, 소모품 교체 등) |


본부 내에는 버킷 외에도 **EM 유닛,** **QA 팀, Cloud DB/Infra 팀, iOS/Android 팀, Web 팀, 정보 보안팀, LiveOps 팀, 엔지니어링 온보딩 팀**이 속해있고, 본부의 미션을 위해 각자 담당하는 업무를 열심히 수행하고 있습니다.

엔지니어링 온보딩 팀은 쏘카 도메인 온보딩 및 기술 온보딩 교육을 통해 쏘카에 새로 합류한 엔지니어의 빠른 적응을 돕습니다.    
엔지니어링 온보딩 팀에서 온보딩 교육을 마치게 되면 각자 희망하는 버킷을 작성한 후 이를 최대한 반영할 수 있도록 조율합니다. 그렇게 버킷 배정을 받아 각 버킷으로 이동해서 주어진 서비스 개발 및 운영을 시작합니다.

<br />

---
## 2. 온보딩 강의

온보딩 커리큘럼은 크게 **온보딩 강의**와 **Dogfooding Project**으로 나뉩니다.
온보딩 강의는 1주 단위로 총 3개의 파트가 진행되고 이후 Dogfooding Project를 2~3주간 수행합니다. 온보딩 당시 전사 재택 기간이라 강의는 모두 비대면으로 진행되었고 추후 녹화본이 공유되었습니다.

이때, "FrontEnd 개발 직무와 BackEnd 개발 직무 별로 교육의 차이가 있을까?"라는 의문점이 생길 수 있습니다. 정답은 **‘공통 교육은 필수이고, 다른 직무의 교육은 선택’**입니다. 
동기 중 BackEnd 개발하는 분들은 FrontEnd 교육도 수강했는데 이후 Dogfooding 프로젝트 진행에 있어 BackEnd ↔️ FrontEnd 간 원활한 협업에 도움이 되었다고 합니다.

이후 작성한 내용은 주 단위로 나눠서 작성했습니다.

### 2.1. 프로그래머의 기본 & 쏘카의 Service Architecture 

1주 차 강의는 **프로그래머의 기본과 쏘카 서비스 아키텍처**가 중점입니다.

| <center>주제</center>                    | <center>내용</center>                                                          |      소속      |   강사   |
| :-- | :-- | :--: | :--: |
| 쏘카 Business Introduction               | 쏘카는 어떤 일들을 하고 있을까요?                                              |     EM 유닛     | 케이제이 |
| 프로그래머로 산다는 것                   | 어떤 개발자가 좋은 개발자인지 함께 고민해 보아요.                                      |      CTO       |   람다   |
| Service Engineering - How To Work        | 서비스 엔지니어링 본부에서 어떻게 일하고 있을까요?                             |     EM 유닛     | 케이제이 |
| 90 Days Planning 작성 가이드             | 90 Days Planning 이란 무엇이고, 어떻게 작성하면 될까요?                         |     EM 유닛     | 케이제이 |
| Service Architecting Model               | 현재 서비스의 Architecture와 추후 지향하는 방향을 소개합니다.                 |   SE 본부장    |  아나킨  |
| Service Engineering - How To Work (Jira) | 쏘카가 사용하고 있는 Jira의 기초 / 심화 기능 사용법에 대해 설명합니다.                |      QA 팀      |   딕키   |
| Service Architecture AS-IS               | 쏘카의 카셰어링 사례를 통해 현재와 미래의 쏘카 Architecture를 공유합니다. | Sharing 그룹장 |  브래드  |

![람다가 생각하는 '좋은 프로그래머'](/img/onboarding-service-engineering/6.png)*람다가 생각하는 '좋은 프로그래머'*

1주 차 강의 중 가장 인상 깊었던 강의는 람다의 **`프로그래머로 산다는 것`** 입니다. 제가 지금까지는 단순히 개발만 잘하는 프로그래머가 되고 싶었는데 이 강의를 통해 **좋은 프로그래머**로 성장해나가는 명확한 목표를 설정할 수 있었습니다. 덧붙여서 **지식 공유 및 협업** 을 위해 고민하고 실천해나가는 자세를 가지고 쏘카에서 열심히 해야겠다는 열의도 생기게 되었습니다.

 
강의 중 **`90 Days Planning 작성 가이드`** 는 서비스 엔지니어링 본부에서 시행하고 있는 개개인 별 분기 단위 마일스톤을 작성하는 것으로, 자기발전을 위한 업무, 개인 활동 등 정량적 목표를 자유롭게 적을 수 있습니다. 
또한 작성했던 계획의 실천을 위해 TL(Tech Lead)에게 공유하고 미팅하면서 업무 일정을 조율할 수 있습니다. **‘주도적으로 일하고 성장하기’**의 목표를 지닌 ‘90 Days Planning’ 덕분에 작성했던 마일스톤을 자유의지로 실천하려는 노력이 있었고, 현재의 저는 작성하기 이전보다 한 층 더 성장한 것을 체감하고 있습니다. 

![3Q 90 Days Planning 작성한 내용](/img/onboarding-service-engineering/5.png)*3Q 90 Days Planning 작성한 내용*

이전까지는 그저 시키는 업무와 주어진 범위까지만 생각하며 일해왔었는데 작성한 planning을 가지고 TL 미팅을 하면서 **‘이번 분기에는 내가 어떠한 업무를 왜 하는지, 어디까지 하고 싶은지’**를 객관적으로, 명확하게 파악할 수 있었습니다. 덕분에 플래닝 한 업무의 우선순위를 부여하고, 저의 일정과 능력에 맞게 스케줄링(Scheduling) 하는 주도적인 자세로 일할 수 있었습니다.  
이에 더해, **‘Personal Growth’**를 작성하며 **‘제 자신, 제 역량을 성장시키기 위해’** 무엇을 하면 좋을지 고민해 볼 수 있었습니다. 그렇게 작성한 목표 달성을 위해 업무 시간 중 일부를 사용하도록 TL이 장려해서 입사 후부터 걱정했었던 개인의 성장을 해결하고 있습니다.

### 2.2. BackEnd 강의 & 쏘카의 개발 문화

| <center>주제</center>                   | <center>내용</center>                                                                                         |    소속     |     강사     |
| :-- | :-- | :--: | :--: |
| Service Development Introduction        | 쏘카의 Service Repository 구조, 개발 환경(Dev, QA/Stage, Production), 개발부터 배포까지의 과정을 소개합니다.  | Car Sharing |     믈브     |
| BackEnd  Running Services In The Local | 실제 운영 중인 쏘카 서버의 Repository를 받아 Local 환경에서 실행하기 위한 과정을 환경설정과 함께 실습해 봅니다. | Car Sharing |     믈브     |
| Github and PR and Reviewing             | 쏘카의 Github 관리 및 협업(PR / Code Review / Merge) 방식을 듣고 실습하는 시간입니다.                         | Car Sharing |     믈브     |
| BackEnd - Coding: Convention and Styles | Kotlin 기본 코딩 가이드 및 IntelliJ Plugin(+ Gradle) 활용 방법을 설명합니다.                                  | Car Sharing |     믈브     |
| BackEnd - Tests And Testable Code       | 테스팅에 대해 배우고, 실습을 통해 테스트 코드를 작성해봅니다.                                                 |     B2B     |     카이     |
| Homework                                | 쏘카 서버의 Repository에서 서비스 하나를 선택해서 Test Code 작성 / PR / Code Review 해보기.                   |             |              |
| BackEnd - CI/CD                         | 품질관리 및 배포/운영까지 함께하는 CI/CD와 쏘카는 어떤 방식인지 설명합니다.                                   |  Marketing  | 도가, 브루스 |
| BackEnd - Datadog & Monitoring          | 쏘카 서버를 모니터링하고 관리할 수 있는 Datadog, 그 외 모니터링 도구에 대해 설명합니다.                       |  Marketing  | 도가, 브루스 |
| BackEnd - Performance Testing           | 내가 만든 서비스가 얼마까지 버틸 수 있는지 알기 위해 수행하는 Performance Testing을 배웁니다.                 |  Marketing  | 도가, 브루스 |


2주 차에는 BackEnd 기술 관련 강의와 함께 쏘카의 협업 문화와 개발 문화를 배울 수 있었습니다. 이와 더불어 개발 환경 설정까지 진행했는데 그 덕분에 이론으로 배운 것을 실제로 연습해 볼 수 있었습니다.

가장 흥미로웠던 강의는 **`BackEnd - Datadog & Monitoring`** 과 **`BackEnd - Performance Testing`**, 마지막으로 **`BackEnd - Tests And Testable Code`** 였습니다.
![쏘카의 Datadog Profiling 일부 화면](/img/onboarding-service-engineering/7.png)*쏘카의 Datadog Profiling 일부 화면*

도가와 브루스가 해주신 **Datadog** 강의를 통해 다음과 같은 다양한 Datadog 활용 사례를 배울 수 있었습니다. 
- 쏘카 서버 대시보드
- Error 발생 시 Slack / Opsgenie 툴과 연동해서 alert을 받을 수 있는 Monitors(APM / Metric 등) 
- Kubernetes Container / Pod / Cluster Monitoring


![Locust를 활용한 Performance Testing 결과 지표](/img/onboarding-service-engineering/8.png)*Locust를 활용한 Performance Testing 결과 지표*

 `Locust`를 이용한 Performance Testing을 통해 실제 내가 만든 서비스가 쏘카 서버에서 버틸 수 있는지, 트래픽을 얼마까지 받아낼 수 있는지 등 성능을 측정해 볼 수 있어 흥미로웠습니다.

마지막으로 **`BackEnd - Tests And Testable Code`** 강의는 TDD 방식 및 테스트 코드 작성의 중요성을 다시금 상기시키게 해준 강의였습니다. 
특히 JUnit의 변천사도 설명해 주시고 실제 쏘카에서 사용하는 컨벤션에 맞게 Unit Test와 Integration Test를 만들어볼 수 있었습니다.

### 2.3. FrontEnd 강의 & 쏘카의 Infra와 DB 


| <center>주제</center>                    | <center>내용</center>                                                                        |     소속      |  강사  |
| :-- | :-- | :--: | :--: |
| FrontEnd  Coding: Convention And Styles | Backoffice 개발 역량을 위한 FrontEnd 기본 코딩에 대해 설명합니다.                            |     Web 팀     | 라파엘 |
| FrontEnd - Package Management            | npm이 무엇인지 설명하고, FrontEnd의 공통 npm module 사용법을 실습합니다.                     |      B2B      |  블랑  |
| FrontEnd - Running Services In The Local | local 환경에서 BackEnd 서비스와 직접 실행해 연동하고, 결과를 확인해 보는 실습하는 시간입니다. |  Car Sharing  | 리스본 |
| FrontEnd - CI/CD                         | FrontEnd의 CI/CD에 대해 설명을 듣고, 개발부터 코드 리뷰 / 배포까지 직접 실습하는 시간입니다.  |   Marketing   | 버틀러 |
| AWS And GCP In SOCAR                     | AWS와 GCP를 쏘카에서는 어떻게 활용하는지 소개합니다.                                         |               |  에코  |
| (Kubernetes) How To Use In SOCAR         | Kubernetes(K8S)의 기본 개념과 원리에 대해 설명을 듣고, 실습을 통해 명령어를 익힙니다.       | Core Platform | 코알라 |
| SOCAR Network                            | 쏘카 서버의 Network Architecture에 대해 소개합니다.                                          | Cloud Infra 팀 |  로원  |
| SOCAR Database Structure                 | AWS RDS를 활용하는 쏘카의 Database Architecture에 대해 소개합니다.                           |  Cloud DB 팀   | 제이든 |
| DB - SQL Basic Grammar                   | 실제 쏘카에서 활용하는 SQL 문법을 보고 작성해 보는 시간입니다.                                |  Cloud DB 팀   |  알티  |


마지막 3주 차 교육은 FrontEnd 관련 강의가 절반을 차지했습니다. 서버 개발자라고 해서 BackEnd만 알고 있는 것보다 쏘카에서의 FrontEnd 개발 문화도 알아두는 것이 이후 협업에 있어 큰 도움이 될 것이라고 판단해서 전부 수강했습니다. 
쏘카에서 FrontEnd 개발은 주로 `react`와 `typescript` 를 사용하는데 저는 개인적으로 `Vue.js` 를 사용해 본 경험이 있어 강의를 이해하기 한결 수월했고 관심 있게 수강했습니다.

그리고 인프라 네트워크 구조와 `AWS RDS` 를 사용하는 쏘카의 DB 구조도를 보며 쏘카 전체 DB 구조에 대해 설명을 들었는데 관련 지식이 부족하다보니 이해하지 못하고 놓친 부분이 있었습니다. 그래서 강의가 끝나고 개인적으로 공부하며 DB와 인프라 구조를 이해하려고 노력했습니다.

이렇게 총 3주간의 온보딩 강의 수강이 끝나고 ~~(쉴 틈 없이)~~ 다음 온보딩 과정인 **‘Dogfooding Project’**를 시작하게 되었습니다! 

<br />

---
## 3. Dogfooding Project

### 3.1. Dogfooding 이란?

대략 3주간의 개발 교육을 마친 후에 온보딩 동기 4명이 한 팀을 이뤄 Dogfooding Project를 수행하게 됩니다. 
Dogfooding은 **‘자사의 제품(소프트웨어)을 직원들이 직접 사용해 보고 개선하는 것’** 을 뜻합니다. 이 프로젝트를 수행하는 취지는 크게 세 가지입니다.

- 피드백을 통해 소프트웨어 개발 기술을 객관적으로 측정하고 성장한다.
- 쏘카의 서비스를 파악하고 개선점을 찾아 더욱 서비스를 발전시킨다.
- 실제 쏘카 서비스에 상용화되기 때문에 프로젝트에 대한 열정과 동기가 생긴다.

저희가 수행하게 된 Dogfooding Project의 명칭은 ‘**RFC103 - CDN 및 업로드 관리’**입니다.

> **RFC(Request For Comments)란?** <br> 
> 새로운 연구 / 기술 / 서비스를 작성하고 동료들에게 공유하며 의견을 받기 위한 문서를 뜻합니다. 의견을 바탕으로 최종 승인된 문서는 더 이상의 수정이 불가능하고 공식적인 표준 가이드로 활용됩니다.)

이 프로젝트의 목적은 다음과 같습니다.
![‘RFC103 - CDN 및 업로드 관리’ 프로젝트 목표](/img/onboarding-service-engineering/9.png)*‘RFC103 - CDN 및 업로드 관리’ 프로젝트 목표*

- AS-IS : 현재 외부로의 노출 또는 제공이 필요한 디지털 에셋(이미지, PDF 파일 등)을 제공하는 일관된 방식이 존재하지 않는 상황입니다.
- TO-BE : **디지털 에셋을 관리하는 독립적인 시스템을 구축**하여 정해진 규칙과 규격에 맞게 관리할 수 있습니다.

애자일 방식으로 1주 단위의 스프린트 3회에 걸쳐 총 3주간 진행된 이 프로젝트의 결과부터 말씀드리자면, **최종 데모까지 성공적으로 마무리했습니다.** 

### 3.2. Kick-Off 미팅

프로젝트 일정 첫날 오전에는 **Dogfooding 사전 미팅**을 통해 작성자인 아나킨에게 전체적인 설명을 듣고 **Kick-Off 미팅**을 가졌습니다. Kick-Off 미팅에서 제일 중점으로 둔 부분은 **‘협업을 위한 프로젝트 싱크 업(Sync-Up)'**입니다.
서로가 똑같이 프로젝트에 대해 이해하고 목표를 수립해야 원활한 협업을 할 수 있다고 판단하여 아래와 같은 세 가지 어젠다를 가지고 미팅을 진행했습니다.

1. 구현해야 할 기능을 RFC 문서에서 도출하여 유저 스토리를 작성하고 스토리 별 FrontEnd / BackEnd 필요한 개발 사항을 정리했으며, 프로젝트 성공 목표와 함께 전반적인 내용을 싱크 업 했습니다.
2.  언어 / 프레임워크 / 라이브러리뿐 아니라 서버 환경 구성 및 시스템에 필요한 AWS 서비스를 리스트 업(List-Up) 했습니다.
3. 주어진 일정을 파악하여 전체적인 플래닝을 세웠고 스프린트 단위 선정 및 스프린트 별 목표를 설정했습니다.

BackEnd는 현재 쏘카 전반적으로 사용하고 있는 언어인 `Kotlin` 과 `Spring Boot framework` 를 사용했습니다. 이에 더해 디지털 에셋을 저장하기 위해 `AWS S3`, 디지털 에셋을 표면적으로 노출시키기 위해 `AWS CloudFront`, 업로드 / 삭제 와 같이 디지털 에셋의 변경 이력을 기록해두기 위해 `Amazon DynamoDB`를 사용하기로 결정했습니다. 저로서는 실무에서 처음 접해보는 서비스였기 때문에, 퇴근 후에 개인적으로 공부하며 이를 활용할 수 있게 노력했습니다.

### 3.3. 프로젝트 진행

이후에는 첫날에 협의한 일정대로 프로젝트를 진행했습니다. `Jira`에서 스프린트를 생성하고 각자 맡은 업무를 티켓으로 만들어 주도적으로 개발했습니다. 그리고 매일 정해진 시간에 데일리 스크럼을 하면서 그날의 업무와 개발 관련 협의가 필요한 사항을 공유했습니다. 

예를 들면 **코딩 컨벤션, 프로젝트 구조 설계, 유저 시나리오, API 명세, CI/CD 환경설정** 등이 있었는데 스크럼 이후 미팅을 통해 가장 효율적이고 최적의 방안을 도출했습니다. 물론 미팅마다 회의록 및 협의 결과를 노션 문서에 기록했습니다.

프로젝트에서 직무 별 수행했던 개발 사항은 다음과 같습니다.  
(작성한 순서대로 순차적으로 수행하진 않았습니다.)

- BackEnd - 코기, 이누, 키이라
    - Amazon S3 연동 환경 구축 / 에셋 파일 S3 버킷 업로드
    - Git Action / Husky / Ktfmt 설정
    - 에셋 파일 삭제
    - 에셋 파일 로그 조회
    - DynamoDB, CloudFront 생성 및 연동 / DynamoDB 활용해서 에셋 파일 로그 저장
    - 에셋 파일 조회
    - Testcontainer, Localstack 모듈 구현
- FrontEnd - 도시
    - Wireframe 작성 / FrontEnd 개발 환경 구현
    - 디자인 토큰 정의 및 설정
    - UI 단위 컴포넌트 및 관련 기능 구현

저희 모두 테스트 코드 작성에 진심이었기 때문에 작업 기간 중 절반은 거의 테스트 코드 작성에 할애했습니다. Unit Test 관련해서 Service는 `kotest`의  `AnnotationSpec` 을, Controller는 `MockMvc`를 사용했습니다. 
이에 더해 AmazonS3 Integration Test를 위해서 `Testcontainer`로  `Localstack` 모듈을 사용하기도 했습니다.

### 3.4. 스프린트 데모

이렇게 정신없이 첫 스프린트를 마친 후 `스프린트 데모`와 `스프린트 회고 및 플래닝` 시간이 되었습니다.

총 3번의 데모를 통해 아래 리스트와 같이 정의했던 **프로젝트의 인수 조건(Acceptance Criteria)**에 대한 개발을 시연했습니다. 데모 시연은 도시가 `localhost` 환경에서 진행해 주셨습니다.

- **쏘카 운영자는 Admin Website를 통해 Public 한 디지털 에셋을 관리하고 싶다.**
    - ‘디지털 에셋 관리 화면’에서 업로드한 에셋 파일을 볼 수 있어야 한다.
    - 에셋 파일을 미리 보기로 볼 수 있어야 한다.
    - 에셋 파일을 업로드할 수 있어야 한다.
    - 에셋 파일을 검색할 수 있어야 한다.
    - 에셋 파일을 삭제할 수 있어야 한다.
    - 에셋 파일을 담는 폴더(디렉토리)를 생성할 수 있어야 한다.
- **쏘카 운영자는 에셋 파일의 History를 저장한 Log를 보고 싶어 한다.**
    - 운영자는 에셋 파일의 변경(생성, 삭제) 이력과 변경한 사람 / 변경일자 / 변경 사유에 대해 알 수 있다.
    - 운영자는 전체 Log에 대해 날짜 기준으로 조회할 수 있다.

<br />

첫 데모 당시에는 많이 긴장했고 떨렸지만 서비스 추가 및 개선 관련 Q&A 시간까지 무사히 마칠 수 있었습니다.

![스프린트 데모 시연](/img/onboarding-service-engineering/10.png)*스프린트 데모 시연*


### 3.5. 회고 및 플래닝

데모 다음 날 스프린트 회고 및 플래닝을 진행했습니다. 스프린트 회고 방식은 `KPT 회고 방식` 을 도입하였습니다.

> 💡 KPT 회고란? **Keep / Problem / Try** 의 세 가지 관점으로 분류하여 회고를 진행하는 회고 방법론입니다.
> - Keep - 잘하고 있는 점 또는 이대로 유지했으면 좋겠다고 생각되는 점
> - Problem - 문제라고 생각되는 점 또는 개선했으면 하는 점
> - Try - 잘하고 있는 것을 유지하기 위한 방법 또는 문제를 해결하기 위한 방법

![KPT 회고](/img/onboarding-service-engineering/11.png)*KPT 회고*

이처럼 스프린트를 진행하면서 느꼈던 Keep, Problem, Try를 스프린트 참여자들이 포스트잇에 작성하고 이를 공유하며 토론을 통해 내용을 개선했습니다. 이후 투표를 통해 다음 스프린트에 수행할 **Action Item**을 선정하는데, 회고의 사회자가 다음 스프린트 기간 동안 Action Item을 잘 수행하는지 감독하게 됩니다.

저희 모두 처음 해보는 회고 방식이어서 퇴근 시간이 가까워질 때가 돼서야 위와 같이 간결하게 정리하고 마칠 수 있었습니다. 다음 회고에서는 **소요시간은 줄이고 회고 목적에 맞게 적합한 Item을 도출해 내는** 노하우가 생겼고, 이는 이후 버킷에서 진행한 스프린트 회고에 있어 큰 도움이 되었습니다.

이렇게 이전 스프린트 회고를 마치고 바로 다음 스프린트를 위한 플래닝을 진행했습니다.
![jira 를 활용한 플래닝](/img/onboarding-service-engineering/12.png)*jira 를 활용한 스프린트 플래닝*

처음 작성했던 유저 스토리를 바탕으로 스프린트 업무 범위를 구체화한 후 티켓을 함께 생성하며 업무 분배를 했습니다. 이때 각 티켓 별로 협의를 통해 최종 Story Point를 확정합니다.

> 💡 Story Point 란?  
> → 지라 티켓에서의 Story Point는 **해당 티켓을 완료하는 데까지 걸리는 노력(시간, 난이도 등)의 총합** 을 의미합니다. 

스프린트 도중에 하게 된 모든 미팅과 회고 / 플래닝은 넉넉하게 시간을 두고 진행했습니다. 
그 이유는 동료들이 자유롭게 의견을 공유하도록 하기 위해서입니다. 그 결과로 프로젝트 기간 동안 충분한 소통을 하며 성공적으로 마무리할 수 있었습니다.
<br />

---
## 4. 동료와의 교류 및 스터디

당연히! 온보딩 강의를 듣고 프로젝트를 수행하는 교육만 받지 않았습니다. 쏘카에서 저희 온보딩팀도 참여할 수 있는 활동이 여러 가지가 있습니다만, 가장 기억에 남는 세 가지 활동에 대해 소개하려고 합니다.

### 4.1. 서비스 엔지니어링 본부 타운홀 미팅 자기소개

서비스 엔지니어링 본부에서는 매달 말일에 한 시간 정도 모두가 모여 서로 인사하고, 정보 / 기술 / 성과를 공유하는  **`서비스 엔지니어링 본부 타운홀 미팅`** 이 있습니다.
매 회차마다 있는 **‘신규 동료 소개’** 세션에서 저에 대한 소개 자료를 PPT 1페이지 분량으로 준비해서 **자기 PR**할 수 있었습니다.
![코기는 이런 사람입니다.](/img/onboarding-service-engineering/13.png)*코기는 이런 사람입니다.*

이렇게 마련해 주신 세션 덕분에 서비스 엔지니어링 본부 동료분들에게 **‘코기’**에 대해 알릴 수 있는 기회가 되었고 다들 뜨거운 박수와 환호로 맞이해주셨습니다.  
(질문도 엄청 해주셔서 Q&A 타임이 되었습니다.)

특히 **‘쏘카에 입사한 것을 진심으로 환영하고 축하한다.’**는 따뜻한 말이 지금까지도 가슴속에 자리 잡고 있습니다. 이러한 세션 덕분에 동료들과 더욱 가까워졌고 회사 또한 빠르게 적응할 수 있었습니다. 

### 4.2. 쏘풍 데이

올해부터 **쏘카 회사 적응 및 동료 간의 친목 도모**를 위해 **`쏘풍 데이`** 가 추진되었습니다.
다른 팀의 동료분들과 하루 종일 식사하고 액티비티 활동을 하면서 더욱 가까워질 수 있는 날입니다. 

이날에는 업무를 하지 않고 쏘풍 데이에 집중할 수 있는 환경을 조성해 주기 때문에 편하게 시간을 보낼 수 있었습니다. 
저희 조는 '브런치 → 영화 → 볼링 → 북 카페' 코스로 활동을 기획했습니다.  
*(다른 조는 양평 두물머리 드라이브, 강원도 바다멍 여행, 남양주 물의 정원, 낙산공원과 연극 등 다양한 활동을 했다고 합니다.)*

![쏘풍 데이 중 볼링 치는 모습](/img/onboarding-service-engineering/14.png)*쏘풍데이 중 볼링 치는 모습*

이런 날을 제공해 준 쏘카 덕분에 잊지 못할 추억을 하나 간직할 수 있었고 다음에 다른 본부와도 쏘풍 데이를 함께하면 좋겠다고 느꼈습니다.

### 4.3. 스터디

쏘카에서는 다양한 주제로 자유롭게 스터디를 만들어 진행할 수 있습니다. 저는 온보딩 기간에 개인적으로 `kotlin in action` 책을 혼자서 공부하다가 버킷에 배정받은 이후에는 MSA 스터디에 참여하여 동료들과 함께 `마이크로 서비스 도입, 이렇게 한다.` 책으로 공부하고 있습니다. 

![온보딩 팀 스터디 진행 리스트](/img/onboarding-service-engineering/15.png)*온보딩 팀 스터디 진행 리스트*

<br />

---
## 5. 온보딩 졸업 후 각자 버킷으로

프로젝트 최종 데모를 끝으로 모든 온보딩 교육 일정을 마쳤습니다. 이후 티타임을 가지면서 각 버킷에 대해 어떠한 서비스와 프로젝트를 진행하는지 소개를 듣고 희망하는 버킷을 3순위까지 작성했습니다.
한 가지 아쉬운 점은 원하는 버킷이 있어도 다른 버킷의 인원이 해당 버킷의 인원보다 적거나 추가 인원이 필요한 경우에만 TO가 생기고, 이러한 **TO가 나온 버킷에만 희망이 가능**했다는 것입니다.

이 때 EM(Engineering Manangement) 유닛의 케이제이가 개인과 각 버킷 별 TL의 희망 순위가 모두 반영될 수 있도록 최대한 조율해 주셨습니다.

그렇게 저는 제가 희망했던 B2B 버킷에 배정받았습니다. 이후 서로 모르는 부분이 있거나 다른 버킷의 서비스와 연관된 기능을 개발할 때에 버킷 간 편하게 교류할 수 있었습니다. 
이는 모두 온보딩 교육이 있었기에 가능했다고 생각합니다.

<br />

---
## 6. 나날이 발전하는 온보딩 커리큘럼

쏘카의 온보딩 커리큘럼은 피드백을 통해 지속적으로 개선되고 있다고 합니다. Dogfooding Project 기간이 짧다는 피드백을 반영하여 현재는 **Dogfooding Project를 2달 가까이 진행**하고 있으며, 기존 커리큘럼에 아래 강의들이 추가되었다고 합니다.

| <center>주제</center>               | <center>내용</center>                                                          |        소속        |  강사  |
| :-- | :-- | :--: | :--: |
| CITY DILEMMA : 쏘카 다큐멘터리 시청 | 쏘카가 추구하는 방향과 지금까지 달려온 여정을 담은 다큐멘터리를 시청합니다.    |                    |        |
| 차량 시뮬레이터 온보딩              | 본부 별 차량 시뮬레이터 체험 & 교육                                            | 커넥티드디바이스팀 |  라네  |
| Modern Architecture 1, 2            | 아키텍트의 역할과 아키텍트는 어떻게 만들어지는지에 대한 이야기를 전해드립니다. |     SE 본부장      | 아나킨 |
| 당신이 모르던 코틀린                | 코틀린에 대한 기초 및 심화 교육                                                |      외부강사      | 오현석 |

<br />

---
## 7. 나에게 온보딩 교육이란?

쏘카에서는 같은 달에 입사한 분들과 함께 온보딩 교육을 받기 때문에 입사 동기가 있습니다.

![신규 입사자 4명 프로필](/img/onboarding-service-engineering/1-4.png)*왼쪽부터 코기, 도시, 이누, 키이라입니다.*

저와 함께 우당탕탕 했던 동기들에게 온보딩 교육 관련해서 Q&A 하는 인터뷰를 진행해 봤습니다.
<br />
*(인터뷰 질문에 성실히 대답해 주셔서 감사합니다!)*

<br />

**Q. 나에게 있어 쏘카의 온보딩 교육이란?**

**코기** : 쏘카에 동화되어 진정한 쏘카 일원으로 합류하게 만들어 주었습니다. 또한 온보딩 교육이 없었다면 평생 갈 소중한 동기를 얻지 못했을 것이라고 생각합니다.

**도시** : 쏘카 문화에 적응하며 동료들과 밍글링(Mingling) 할 수 있는 즐거운 시간이었습니다.

**이누** : 쏘카에 자연스럽게 적응할 수 있는 따뜻하고 즐거운 시간이었습니다.

**키이라** : 쏘카 문화에 스며들고 쏘카의 기술들을 천천히 살펴볼 수 있는 시간뿐 아니라 나에게 필요한 것들을 파악하고 준비할 수 있는 시간이었습니다. 이에 더해, 동기 및 쏘카 동료들과 친해질 수 있는 시간이었습니다.

<br />

**Q. 온보딩 교육을 통해 어떤 도움을 받았나요?**

**코기** : 온보딩 교육 이후 저의 직업을 ‘백엔드 서버 개발자’라고 자신 있게 소개할 수 있었습니다. 그만큼 더 깊고 전문적인 지식과 경험을 쌓는데 발판을 마련해 줬고, ‘넌 쏘카에서 충분히 잘 해낼 수 있는 사람'이라는 생각을 자리 잡게 해주었습니다.

**도시** : 쏘카의 개발 문화와 추구하는 가치를 체계적으로 알 수 있었고 여러 분야의 전문가분들에게 직접 관련 지식과 경험을 배울 수 있던 점이 저에게 많은 도움이 되었습니다.

**이누** : 체계적인 개발 수업을 들으며 개발자로서의 기반을 닦을 수 있었습니다. Dogfooding 프로젝트를 하며 쏘카 내에서의 협업은 어떻게 이뤄지는지, 이슈가 발생했을 땐 어떻게 핸들링해야 하는지, 개발 및 업무 진행에 있어 도움은 어떻게 받을 수 있는지 등 을 배울 수 있었습니다. 가장 큰 건 무엇보다 소중한 동기들을 얻은 것입니다.

**키이라** : 쏘카가 추구하는 개발 방향에 대해 전반적으로 파악할 수 있었고 무엇보다 Dogfooding 프로젝트를 진행하면서 협업 방식과 의사소통 방식을 배울 수 있었습니다. 이는 각자 버킷에 배정된 이후에도 빠르게 적응할 수 있는 기반이 되었다고 생각이 듭니다.

<br />

**Q. 가장 인상 깊은 온보딩 교육은 어떤 것인가요?**

**코기** : 교육받는 모든 순간이 전부 기억에 남았고 인상깊었습니다.

**도시** : 함께 3월에 입사한 동기들과 함께 진행한 **`Dogfooding 프로젝트`** 가 가장 기억에 남습니다. 이 프로젝트를 진행하면서 온보딩 강의로 배웠던 쏘카의 애자일 문화를 실제로 사용해 볼 수 있었고, 이후에는 실제 쏘카에서 사용하기 위한 목적이었어서 쏘카와 관련된 도메인 지식을 익힐 수 있었습니다.

**이누** : 모든 교육이 개성 있고 유익했습니다.

**키이라** : 음.. 온보딩 기간 동안 협업 방법, Architecturing Model, CI/CD, 서버 모니터링, Test Code 등 다양한 강의를 수강했고 Dogfooding 프로젝트를 진행했습니다. 사실 이러한 온보딩 프로세스가 체계적으로 구성되어 있다는 점에 굉장히 만족했습니다. 또한실제로도 교육받은 내용들이 온보딩 이후 팀에서의 적응을 수월하게 해주었습니다.

이 중 가장 인상 깊었던 온보딩 교육을 꼽자면 **`Dogfooding 프로젝트`** 인 것 같습니다. 직접 경험해 보는 것만큼 이해가 잘 되는 것은 없으니까요. 프로젝트 과정을 통해서 실제로 쏘카에서 쓰이는 기술들을 미리 찾아보고 적용해 볼 수 있었던 시간이어서 많은 도움이 되었습니다. 마지막으로 동기들과 같이 진행했던 프로젝트가 현재 저희 Marketing Bucket으로 넘어왔는데, 고도화 후 쏘카 서비스에 얼른 적용시켜보고 싶습니다.

<br />

**Q. 그렇다면, 현재 배정받은 버킷에서 업무를 하는 데 있어 가장 크게 도움 되었다고 생각되는 강의와 그 이유가 궁금합니다.**

**코기** : 저는 도가와 브루스가 강의해 주신 **`BackEnd - CI/CD 및 Datadog & Monitoring`** 강의가 가장 도움이 되었습니다. 현재 B2B 버킷의 서비스를 모니터링하는 **Datadog Monitor 및 Opsgenie 구성**을 수월하게 할 수 있는데 도움이 많이 되었습니다.

**도시** : 저는 경력으로 입사하였지만 쏘카 FrontEnd 직무의 업무방식을 전부 이해하는 것은 아니었기 때문에 **`프론트엔드 직무 관련 모든 강의`** 들이 업무를 이해하는 데 도움이 되었습니다.  
현재는 FrontEnd 개발자로써 Core Platform Bucket과 Web 팀에 소속되어 관련 업무를 하고 있는데, 온보딩 강의를 통해 저의 지금까지의 경험과 쏘카 FrontEnd 직무의 업무방식의 차이를 알 수 있었고, 더 나은 기술 및 개발 문화를 모색할 수 있는 기반을 만들어줬다고 생각합니다.

**이누** : 카이가 해주신 **`BackEnd - Tests and testable code`** 강의가 실무에서 가장 유용한 것 같습니다. 직접 테스트 코드를 짜면서 비즈니스 로직을 파악하고 어떤 상황에서 에러 처리를 해야 하는지 꼼꼼하게 배울 수 있었습니다.

**키이라** : 현재 속한 버킷에서 업무를 하는데 많은 도움이 되었던 강의는 대표적으로 2개가 있습니다. (한 가지만 선택하라고 하셨지만..)

 첫 번째는, **`BackEnd - Runnning Services In The local`** 강의입니다. 이 강의에서 Git 관련 설정부터 로컬에서 서버 띄워보는 작업까지 전부 진행했는데, 처음 슬라이드를 보고 설명을 들었을 때만 해도 간단해 보였습니다. 하지만 처음 Mac 환경 설정부터 시작해서 로컬에서 쏘카 서버를 띄울 수 있는 환경을 구축하기까지 함께 실습해 보면서 만약 이걸 혼자 했다면 무조건 헤맸을 거라는 생각이 들었고, 그와 함께 이 강의에 대한 고마움이 계속 기억에 남아있습니다.  
 두 번째는, **`BackEnd - Tests and Testable Code`** 강의입니다. 이 강의에서는 테스트 코드 종류부터 왜 테스트 코드가 필요한지, TDD 등에 대한 설명과 실습을 수행했습니다. 입사하기 전 따로 프로젝트를 진행해 본 경험은 있었지만 프로젝트에 테스트 코드를 활용해 보지는 않았어서 해당 강의가 도움이 되었습니다. 또한 현재 버킷에서 진행하는 업무의 대부분은 테스트 코드 작성이 필수여서 이 강의를 통해 얻은 지식과 기술을 지금도 계속 사용하고 있기 때문입니다.

제가 백엔드 직무여서 그런지 직무와 관련된 강의들이 조금 더 인상 깊었던 것 같습니다. 하지만 돌이켜보면 온 보딩 강의 중에 저에게 도움이 되지 않았던 강의는 하나도 없다고 생각합니다. 강의해 주신 분들 모두 감사합니다! 

<br />

**Q. 새롭게 합류할 동료에게 해주고 싶은 이야기가 있다면?**

**코기** : 이 글을 보고 합류하셨다면, 댓글을 달아주세요! 너무너무 환영하고, 반갑다는 의미로 식사 한 끼 대접하겠습니다~ 🍚  
(매일매일 모니터링 하고 있겠습니다 👀)

**도시** : 애자일 문화, 개발 문화, 개발자가 일하기 좋은 회사를 찾고 있다면 쏘카로 (당장) 오세요~!

**이누** : 쏘카에 온 걸 환영하고 같이 즐겁게 개발했으면 좋겠습니다! 😊

**키이라** : 성장할 수 있는 회사, 워라벨이 좋은 회사를 찾으신다면, 쏘카에 만족하실 것 같아요~ 👍

<br />

---
## 8. 마치며

회사에서는 같이 협업하고 퇴근 후에는 친목을 다지며 하루하루 행복하게 만들어준 동기들에게 감사 인사를 드리며, 고마움의 표시로 함께 카페에서 추억을 나눴던 사진을 첨부하며 글을 마무리하겠습니다.

![왼쪽부터 도시, 이누, 코기(저), 키이라입니다.](/img/onboarding-service-engineering/16.png)*왼쪽부터 도시, 이누, 코기(저), 키이라입니다.*

<br />

지금까지 긴 글 읽어주셔서 감사합니다.


