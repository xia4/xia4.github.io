---
title: "TIL. RESTful API"
description: "RESTful API > 1. API시스템을 구현하기 위한 아키첵처 중에 가장 널리 사용되는 형식 	Graphql, GRPC, REST...etc Representational State Transfer 	웹상에서 사용되는 여러 리소스를 HTTP URI로 표현하고 그 "
date: 2021-08-08T05:32:05.562Z
tags: ["API"]
---
> ##  RESTful API

1. API시스템을 구현하기 위한 아키첵처 중에 가장 널리 사용되는 형식
	- Graphql, GRPC, REST...etc
2. Representational State Transfer
	- 웹상에서 사용되는 여러 리소스를 HTTP URI로 표현하고 그 리소스에 대한 행위를 HTTP Method로 정의하는 방식
    - 즉, 리소스(HTTP URI로 정의된)를 어떻게한다(HTTP Method + Payload)를 구조적으로 깔끔하게 표현
![](/images/1be52ef0-24fd-441f-b5ae-6d13305cb335-Rest%20API%20Basics.png)

장점: self-descriptiveness, RESTful API 는 그 자체만으로도 API의 목적이 쉽게 이해된다.

단점: 표준규약이 없어, **안티패턴**으로 작성되는 경우가 흔하다.
(안티패턴: 실제 많이 사용되는 패턴이지만 비효율적이거나 비생산적인 패턴)

> ## 기본배경 지식

**URI, HTTP Method, Payload**
1. URI
	- 해당사이트의 특정자원의 위치를 나타내는 유일한주소
    - Https://naver.com/**login**
    - Https://naver.com/**news**
2. HTTP Method
	- HTTP request가 의도하는 action을 정의한 것
3. Payload
	- HTTP request에서 server로 보태는 데이터(body) 
![](/images/af6e7c6b-b896-4193-893c-5907939bb8d9-Rest%20API%20Basics.png)

> ## RESTful API 설계규칙

- URI 정보를 명확하게 표현해야 한다.
-resource는 명사를 사용한다.
ex)GET/user/1 -> GET/users/1

- resource에 대한 행위를 HTTP Method(GET, PUT, DELETE)로 표현한다.
-URI에 HTTP Method가 포함되서는 안된다.
ex) GET delete/user/1 -> DELETE/users/1
-URI에 동사가 포함되서는 안된다.
ex) GET /user/show/1 -> GET/users/1
ex) POST insert/user/2 -> POST/users/2

- resource 사이에 연관 관계가 있는 경우
-/리소스/고유ID/관계 있는 리소스
ex)GET/users/{user_id}/profile

- 파일의 경우 payload의 포맷을 나타내기 위한 파일 확장자를 URI에 포함시키지 않는다.
ex)GET user/1/profile-photo.jpg(X)
ex)GET user/1/profile-photo(이때, payload의 포맷은 headers에 accept를 사용한다)

- URI는 / 구분자로 사용하여 자원의 계층 관계를 나타내는데 사용한다.
- URI 마지막 문자로 /를 포함하지 않는다.
ex)GET users/protfolios/(X)

- _는 사용하지 않는다.
- URI 경로에는 대문자 사용을 피하도록 규정하고 있다. 
- URI는 /구분자를 사용하여 자원의 **계층 관계**를 나타내는데 사용한다.


