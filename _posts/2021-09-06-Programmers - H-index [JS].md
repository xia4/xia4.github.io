---
title: "Programmers - H-index [JS]"
description: "스터디를 시작하면서 알고리즘 푸는 연습을 하게 되었다.알고리즘은 프로그래머스라는 사이트에서 풀고싶은 문제를 풀어보고 블로그에 작성할 계획이다.이번에 풀게 된 알고리즘은 H-index 문제이다.처음 읽어봤을땐 무슨 말인지 잘 이해하지 못한 상태로 코드를 계속 잘못 짰다."
date: 2021-09-05T09:53:25.134Z
tags: ["알고리즘"]
---
스터디를 시작하면서 알고리즘 푸는 연습을 하게 되었다.
알고리즘은 프로그래머스라는 사이트에서 풀고싶은 문제를 풀어보고 블로그에 작성할 계획이다.

이번에 풀게 된 알고리즘은 H-index 문제이다.

> ## H-index

![](/images/064d706a-edfd-455d-b2c1-6629f201b5ab-image.png)

처음 읽어봤을땐 무슨 말인지 잘 이해하지 못한 상태로 코드를 계속 잘못 짰다. 문제부터 이해해야겠단 마음으로 H-index부터 무엇인지 알아보았다.[Wikipedia] (https://en.wikipedia.org/wiki/H-index) [연구논문?](https://www.ibric.org/myboard/read.php?Board=news&id=270333) 등 많이 찾아봤다.

서론이 너무 길었다. 

> ### 문제풀이
![](/images/1b34dd0d-f1a6-45a9-a4d6-7897713b02df-image.png)
* sort로 배열을 내림차순 정렬했다.
* index + 1 <= array[idx]를 만족하는 마지막 인덱스는 2이다.
* H-index는 2이다.




