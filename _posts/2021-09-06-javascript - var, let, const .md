---
title: "TIL. javascript - var, let, const "
description: "var, let, const 차이점var, let은 변수 선언시 초기 값을 주지 않아도 되지만 const는 반드시 초기값을 할당해야 합니다.var는 function-level scope이고, let,const는 block-level scoped이다.그럼 function"
date: 2021-06-16T09:57:27.074Z
tags: ["JavaScript","const","hoisting","let","var"]
---
> **var, let, const 차이점**

* <code>var</code>, <code>let</code>은 변수 선언시 초기 값을 주지 않아도 되지만 <code>const</code>는 반드시 초기값을 할당해야 합니다.
* <code>var</code>는 <code>function-level scope</code>이고, <code>let</code>,<code>const</code>는 <code>block-level scoped</code>이다.

_그럼 function-level scope 와 block-level scoped 를 알아보자_

## 1. 우선 스코프란?

* 우리말로 번역하면 '범위'라는 뜻을 가지고 있다. 즉, 스코프란 '변수에 접근할 수 있는 범위'라고 할수있다.
* 자바스크립트를 포함한 모든 프로그래밍 언어의 기본적인 개념이다.

## 2. 스코프의 2가지 타입
* _**global(전역)과 local(지역)이 있다.**_
#### 전역스코프(Global Scope)는 말 그대로 전역에 선언되어있어 어느 곳에서든지 해당 변수에 접근할 수 있다는 의미이다.
#### 지역스코프(Local Scope)는 해당 지역에서만 접근할 수 있어 지역을 벗어난 곳에선 접근할 수 없다는 의미이다.

```
var a = 1; // 전역 스코프
function print() { // 지역(함수) 스코프
 var a = 111;
 console.log(a);
}
print();
console.log(a);
```
## 3. 함수 레벨 스코프, 블록 레벨 스코프

>**함수 레벨 스코프(Function-level scope)** 

함수 내에서 선언된 변수는 함수 내에서만 유효하며 함수 외부에서는 참조할 수 없다.즉, 함수 내부에서 선언한 변수는 지역 변수이며 함수 외부에서 선언한 변수는 모두 전역 변수이다.
```
var a = 111;

console.lof(a); // 111

{ 
   var a = 222; //전역 변수
}
console.log(a); // 222
```
* <code>var</code>의 코드 블록 내의 변수 a는 전역 변수이다.<code>var</code>키워드를 사용하여 선언한 변수는 중복 선언이 허용 된다. 단, 코드 블록 내의 변수 a는 전역변수이기 때문에 전역에서 선언된 전역 변수 a의 값 111을 새로운 값 222로 재할당하여 덮어쓴다.


> **블록 레벨 스코프(Block-level scope)**

모든 코드 블록(함수, if 문, for 문, while 문, try/catch 문 등) 내에서 선언된 변수는 코드 블록 내에서만 유효하며 코드 블록 외부에서는 참조할 수 없다. 즉, 코드 블록 내부에서 선언한 변수는 지역 변수이다.

```
let b = 111; // 전역 변수

{
  let b = 222; // 지역 변수
  let bar = 222; // 지역 변수
}

console.log(b); // 111
console.log(bar); // ReferenceError: bar is not defined
```
<code>let</code>키워드로 선언된 변수는 블록 레벨 스코프를 따른다. 코드 블록 내에 선언된 변수 b는 블록 레벨 스코프를 갖는 지역 변수이다. 전역에서 선언된 변수 b와는 다른 별개의 변수이다.

## 4. 호이스팅
함수 안에 있는 선언들을 모두 끌어올려서 해당 함수 유효 범위의 최상단에 선언하는 것을 말한다.

> **호이스팅이란**

자바스크립트 함수는 실행되기 전에 함수 안에 필요한 변수값들을 모두 모아서 유효 범위의 최상단에 선언한다.
즉, 함수 내에서 아래쪽에 존재하는 내용 중 필요한 값들을 끌어올리는 것이다.

* **example**
```
// 함수 먼저
function hello1() {
	console.log('hello1');
}
hello1();

// 함수의 호출을 먼저

hello2();

function hello2() {
	console.log('hello2');
}
```
두개의 예제는 잘 작동된다. 함수만 적용되는것이 아니라 <code>var</code>를 사용한 변수도 적용된다.

```
age = 7;
age++;
console.log(age);

var age;
```

