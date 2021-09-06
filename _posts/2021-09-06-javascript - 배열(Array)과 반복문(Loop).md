---
title: "TIL. javascript - 배열(Array)과 반복문(Loop)"
description: "JavaScript  📏배열(Array)이란?  연관된 데이터를 모아서 통으로 관리하기 위해서 사용하는 데이터 타입이다. 변수가 하나의 데이터를 저장하기 위한 것이라면 배열은 여러 개의 데이터를 하나의 변수에 저장하기 위한 것이라고 할 수 있다.  🔄반복문(Loop"
date: 2021-06-09T14:09:37.028Z
tags: ["JavaScript","반복문","배열"]
---
> **JavaScript**

![](/images/49bb108f-4f7f-4677-a9a9-8ea7bb5c9b3a-Untitled.png)

## 📏배열(Array)이란?

연관된 데이터를 모아서 통으로 관리하기 위해서 사용하는 데이터 타입이다. 
변수가 하나의 데이터를 저장하기 위한 것이라면 배열은 여러 개의 데이터를 
하나의 변수에 저장하기 위한 것이라고 할 수 있다.

#### 배열에 새 항목 추가
배열에 새로운 항목을 추가 할 때에는 배열이 지니고 있는 내장 함수인<code>push</code>함수를 사용한다.
#### 배열의 크기 알아내기
배열의 크기를 알아낼 때에는 배열의<code>length</code>값을 확인한다.
<hr>

## 🔄반복문(Loop)이란?
반복문은 특정 작업을 반복적으로 할 때 사용할 수 있는 구문입니다.

### 반복문의 종류
<ul>
  <li><code>for</code> 특정 값에 변화를 주어가면서 우리가 정한 조건이 만족된다면 계속 반복한다.</li>
  <li><code>while</code> while문 뒤에 따라오는 괄호 안의 조건이 참(true)면 중괄호 안의 코드 구간을 반복적으로 실행한다. 조건이 false면 반복문이 실행되지 않는다.</li>
  <li><code>break</code> 더 이상 반복하지 않고 for문이나 while문을 끝낸다.</li>
  <li><code>continue</code> 반복을 끝내지 않고 특정 조건이 만족 되었을때 그 다음 루프로 실행된다.</li>  
</ul>

### for
```
const names = ['a', 'b', 'c'];
for (let i = 0; i < names.length; i++) {
  console.log(names[i]);
}
```
### while
```
let i = 0;
while (i < 10) {
  console.log(i);
  i++;
}
```
### break, continue
```
for (let i = 0; i < 10; i++) {
  if (i === 2) continue; // 다음 루프를 실행
  console.log(i);
  if (i === 5) break; // 반복문을 끝내기
}
```




<hr>
  


### 배열 내장함수
<ul>
  <li><code>forEach</code><li> 배열안에 있는 원소들을 가지고 어떤 작업을 일괄적으로 하고싶을때 사용된다.
  <li><code>map</code><li> 배열안에 있는 내용을 가지고 전체적으로 변환을 해주고싶을때 사용한다.
  <li><code>filter</code><li> 특정 조건을 만족하는 원소들을 찾아서 새로운 배열을 만든다.
  <li><code>indexOf</code><li> 원하는 항목이 몇번째 원소인지 찾아주는 함수이다.