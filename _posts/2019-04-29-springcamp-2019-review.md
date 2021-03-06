---
layout: post
title: spring camp 2019 참석 후기 (1부)
categories : [Seminar]
comments: true
tags: [Seminar, Spring, Springboot]
---
spring camp 2019를 다녀왔다!  
티켓팅이 정말 어려웠기 때문에, 지인이나 회사의 다른 개발자분이 티켓팅에 실패해서 혼자 다녀왔다.  
공개된 세션들은 지금 내가 개발하고 있는 프로젝트에 많은 도움이 될 것 같아서 정말 기대를 많이 했다.  
특히 `실전에 써먹는 스프링부트` 나 `Monitoring With Actuator`, `무엇을 테스트할 것인가? 어떻게 테스트할 것인가?`, `Kotlin 프로젝트를 피할 수 없을 때` 라는 세션이 그러했다.  
최근 테스트를 내가 제대로 하고 있는지에 대한 의문이 있었고, 모니터링에 대한 필요성을 느끼고 있어서였다.   
Kotlin은 저번에 Springboot에 붙이려다 실패했었기 떄문에 위의 세션이 기대가 됐다.  
세션은 오전 10:40 분 부터 시작했는데 가는길에 시간이 조금 걸려 조금 지각을 해버렸다.  
로비에 들어가니 팔찌와 스티커 그리고 휴대용 선풍기를 줬다(왜인지는 모르겠는데 많은 개발세미나에선 휴대용 선풍기를 준다)
굿즈를 받아들고 Track 1의 `실전에 써먹는 스프링부트`를 들었다.  
중후반에 들어왔기 때문에 아쉽게 기록을 하지 못했다. 정말 아쉬웠다. 

## Monitoring With Actuator
두번째로 들은 세션은 `Monitoring With Actuator` 였다.  
보안에 대한 의문이 있었기 때문에 예전에 한번 도입하려다 그냥 포기했었는데, 이 세션에서 어떻게 사용해야 하며 모니터링을 도와주는 도구 및 팁과룰에 대한 다양한 설명을 들을 수 있었다.  
`Actuator`는 springboot 2.0 부터 사용할 수 있는데, 다행히 저번에 버전업을 해서 도입한다면 바로 도입할 수 있을 것 같았다. 1.5에서도 사용할 수 있지만 제약사항이 많았다.  

### Spring Actuator 란?
* 장애 예방, 원인파악 및 조치, 상태확인, 성능개선, 서비스상태분석을 위함
* 제어 도구  = endpoint
* 지표 제공 = metrics
* 사용중인 라이브러리 탐지도 한다

### default endpoint
* default 는 health, info 만 제공 properties에서 설정할 수 있다.
* Enabling Endpoints
    * web  > rest(health,info)로 보여줌
    * jmx > 셧다운 제외한 모든 정보를 보여줌
    * spring boot 2.0 부터 spring security에 통합 혹은 따로 서버에 띄우는 방법(총 두개)으로 사용 가능
    * 접근 가능 ip 설정 가능

### Metrics
* 2.0 부터 특정 지표상의 key value 쌍의 지표 tag로 검색 가능
* 반드시 측정해야 할 지표 (RED Method)
    * (Request)Rate
    * (Request)Error
    * (Request)Duration

* outcome code => status 간단히 잘 볼수있음

### Micrometer
* Registry, Meter, Tag
* spring boot 2.0부터 지원
* meterregistry cloudwatch도 있음!

## 자바에서 null을 안전하게 다루는 방법
세번째로 들은 세션은 `자바에서 null을 안전하게 다루는 방법` 이었다. 내 생각에, 자바에서 가장 많이 일어나는 Exception은 `nullPointer exception`이 아닐까 싶다.   
인기가 정말 많았던 세션이라 아쉽게도 좌석 부족으로 서서 들어 기록을 하진 못했지만 ppt가 공개되었다! [ppt 링크](https://www.slideshare.net/gyumee/null-142590829)   
너무 너무 유익한 세션이었다. 만약 해당 강연을 듣지 못한 분은 ppt를 보고 이 강연이 얼마나 유익했을지 알 수 있을거라 생각한다.
해당 세션이 끝난 후 한시즈음 점심을 먹었다. 배달의 민족 측에서 준비한 도시락이었다. 보통 세미나에선 샌드위치를 주는데 한식을 줘서 좋았다 :D

## 무엇을 테스트할 것인가? 어떻게 테스트할 것인가?
네번째 세션은 정말 기대하던 TDD 세션이었다. TDD라기보단 테스트 세션이었지만 그래서 더 좋았다.  
그간 인터넷을 찾아보며 나름대로 테스트코드를 작성해오고 있었는데, 맞게 작성하고 있는지, 이건 테스트해야되는지 이건 아닌지, 이걸 테스트하기엔 너무 어려운데 과연 의미가 있는지
이건 불가능한 테스트인데 어떻게 해야 하는지에 대한 고민이 많았다.  
그래서 Udemy에서 [Master Java Unit Testing with Spring Boot & Mockito](https://www.udemy.com/learn-unit-testing-with-spring-boot/?couponCode=SBT-2019) 강의라도 들을까 하고 있던 차에, 한국에서! 그것도 실무자가 하고있는 스프링부트 테스트코드 강의라서 많은 기대가 됐다.   
그리고 이 세션은 그러한 내 많은 고민을 한번에 해결해 주었다! 그리고 나는 테스트코드를 맞게 짜고 있었다. 안도감이 들었다.  
강연 중간에 `spock`에 대한 언급이 있었는데, 생각보다 많은 분들이 사용하고 있어서 왠지 든든했다(?)   
spock는 정말 좋다. 처음엔 groovy가 낯설었지만 조금 적응이 되니 너무 편리했다.  

### 테스트로부터 얻을 수 있는 것
* 안정감과 자신감 (정말 그렇다!)
* 대상은 나와 동료

### 무엇을 테스트 할 것인가
* 기존 플로우 안까지 할 필요없음
* 만약 걔를 테스트해야되면 걔를 빼는게 맞는거임
* 설계사항 그대로 테스트 코드로 옮기는게 좋음

### 테스트 가능한 것 불가능한 것 
* 외부 API 테스트안됨(그렇다)
* 항상 성공할 수 있는것 동일한 결과가 나올 수 있는것을 테스트 

### 어떻게 테스트 할 것 인가
* 바운더리 레이어까지 테스트안되는걸 끌어올려서 테스트
* 바운더리 레이어 = > 한 모듈로서의 의미를 지니는 가장 바깥쪽
* springcontext의 오용은 언어의 본질을 망각하게 될 수 있다.
* Context, framework 종속적이지 않은 테스트를 우선
* Test double
    * 테스트 할 수 없는 영역을 주입해서 테스트할 수 있게 해줌
    * 무엇을 test double로 처리해야할까
    * H2 뭐 그런거 써서 enbedded 활용 => 제어할 수 없던 그 영역을 제어할 수 있다!
* Endpoint Test
* **Spring contract**

# test tip
* 테스트는 상호 독립적으로 작성
* 공유되는 데이터는 꼭 초기화를 한다(테스트간 서로 영향을 끼치지않도록) => Dynamic Test (Junit5)
* 테스트 에서 의도와 목적이 드러나도록
* 테스트 코드도 리펙토링 대상

앞으로 테스트코드를 더 즐겁고 확신있게(?) 짤 수 있을 것 같다.

---
이후에 들은 세션은 `당신도 할 수 있는 레거시 프로젝트 개선 이야기`, `Kotlin 프로젝트 적응하기` 이다.  
`Kotlin + Spring Data JPA` 세션을 듣고싶었는데, 중간에 일이 생겨 아쉽게 마지막 세션을 들을 수 없었다.  
이전에 kotlin 프로젝트에 자바 라이브러리를 사용하려다 대차게 실패한 적이 있기 때문에 꼭 듣고 싶었다.  
해당글 : [Kotlin 에서 Lombok을 사용할 수 없는 문제](https://sehajyang.github.io/etc/2019/03/07/kotlin-and-lombok.html)     
강연 영상이나 ppt가 공개되면 봐야겠다.
