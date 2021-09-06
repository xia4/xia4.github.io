---
title: "TIL. TypeScript"
description: "2012년 마이크로소프트가 발표한 TypeScript는 JavaScript를 기반으로 정적 타입 문법을 추가한 프로그래밍 언어이다.컴파일 언어, 정적 타입 언어JS는 동적타입의 인터프리터 언어로 런타임에서 오류를 발견할 수 있다.TS는 정적 타입의 컴파일 언어이며 타입"
date: 2021-09-06T07:44:48.935Z
tags: ["typescript"]
---
> ## TypeScript에 대해서 알아보자

![](/images/16784050-d803-4c59-a6b8-04f8f8c595d4-Typescript_logo_2020.svg.png)

2012년 마이크로소프트가 발표한 TypeScript는 JavaScript를 기반으로 정적 타입 문법을 추가한 프로그래밍 언어이다.

> ### TypeScript의 특징

* **컴파일 언어, 정적 타입 언어**
    - JS는 동적타입의 인터프리터 언어로 런타임에서 오류를 발견할 수 있다.
    - TS는 정적 타입의 컴파일 언어이며 타입스크립트 컴파일러 또는 바벨을 통해 JS코드로 변환된다.
    - 코드 작성 단계에서 타입을 체크해 오류를 확인할 수 있고 미리 타입을 결정하기 때문에 실행 속도가 매우 빠르다는 장점이 있다.
    - 코드 작성 시 매번 타입을 결정해야 하기 때문에 번거롭고 코드량이 증가하며 컴파일 시간이 오래 걸린다는 단점도 있다.
    
* **자바스크립트 슈퍼셋**
   - TS는 JS의 슈퍼셋, 즉 JS기본 문법에 TS의 문법을 추가한 언어이다.
   - 유효한 JS로 작성한 코드는 확장자를 <code>.js</code>에서 <code>.ts</code>로 변경하고 TS로 컴파일해 변환할 수 있다.
   
* **객체 지향 프로그래밍 지원**
  - TS는 ES6에서 새롭게 사용된 문법을 포함하고 있으며 클래스, 인터페이스, 상속, 모듈 등과 같은 객체 지향 프로그래밍 패턴을 제공
  
> ### TypeScript 설치하기

TS를 설치하는 방법에는 크게 두 가지가 있다.
- npm을 이용한 설치(Node.js 패키지 매니저)
- TypeScript의 Visual Studio 플러그인 설치


1. NPM 사용자의 경우
```
> npm install -g typescript
```
2. TS를 Visual Studio와 함께 설치하지 않았다면 [이곳에서 다운로드](https://www.typescriptlang.org/#download-links)할 수 있다.

## 첫 번째 TS파일 만들기
에디터에서, <code>greeting.ts</code>파일에 Js코드 입력
```
function greeting(preson) {
	return "Hello, " + person;
}
let user = "Jane User";

document.body.textContent = greeting(user);
```

## 코드 컴파일하기
<code>.ts</code>확장자를 사용했지만, 이 코드는 아직 일반 Js코드이다.
커맨드 라인에서 TS컴파일러를 실행하자.
```
tsc greeting.ts
```
Js코드를 포함하고 있는 <code>greeting.js</code> 파일이 생길 것이다.


