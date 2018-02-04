---
title:
categories:
  - Dev
  - C
tags:
  - C 언어
  - 프로그래밍
  - 알고리즘
  - 둠스데이
date: 2016-03-22 18:02:42
thumbnail: /images/thumbnail/dooms.png
---
# 둠스데이 알고리즘 (C 언어)

* [Doomsday algorithm in C language](#Doomsday-algorithm-in-C-language)
	* [What is doomsday?](#What-is-doomsday)
	* [Applying doomsday algorithm](#Applying-doomsday-algorithm)
	* [How to calculate doomsday of the year](#How-to-calculate-doomsday-of-the-year)
	* [Calculate a given date](#Calculate-a-given-date)
	* [Download sample C file](#Download-sample-C-file)



## 둠스데이란?
{% blockquote Wikipedia https://ko.wikipedia.org/wiki/%EB%91%A0%EC%8A%A4%EB%8D%B0%EC%9D%B4_%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98%}
둠스데이 알고리즘(Doomsday algorithm)은 존 호턴 콘웨이가 발명한 알고리즘으로, 임의의 날짜에 해당하는 요일을 쉽게 구하는 데에 쓰인다.
한 해에서 다음 날짜는 언제나 요일이 같다.
{% endblockquote %}

## 둠스데이 알고리즘 적용하기
1. 해당 세기의 **`"기준일"`** 을 찾습니다.
2. 기준일을 이용해서 해당 년도의 둠스데이를 계산합니다.
3. 항상 둠스데이를 만족하는 날짜들중 (4/4, 6/6, 8/8 등) 찾고자 하는 날짜와 가장 가까운 날을 고르고, 해당 날짜와 찾고자 하는 날짜의 차를 구해 모듈로 연산을 합니다 (mod 7, C 언어에선 %7 해서 나오는 값). 해당 값을 세기 기준을에 더하면 날짜가 구해집니다.
![Doomsday_calendar](Doomsday.png)
![Doomsday_Memorable_Date](dooms.png)

## 해당 년도의 둠스데이 계산하기

다음 세기들은 해당 기준일을 가집니다.
1800~1899 는 **금요일**
1900~1999 is **수요일**
2000~2099 is **화요일**
2100~2199 is **일요일**
그리고 그 이후 년도들은 금요일, 수요일, 화요일, 일요일 순으로 계속 반복됩니다.

해당 기준일을 가지고 원하는 년도의 둠스데이를 알아봅시다.
예를들어 **2016년 3월 24일** 의 날짜를 구해보겠습니다.
1. 해당 년도의 끝 2자리 수를 12로 나눕니다. 2016년도는 16을 12로 나눠야 겠죠.
`16을 12로 나누면 1과 나머지 4가 남죠. 여기서 몫을 a 로 나머지를 b라고 하겠습니다.`
1. Divide last two digits of Year with 12 - YYYY -> YY**YY** / **12** -> a...b
`2016-> 16/12 = 1 ... 4 as remainder ( a is 1 and b is 4 )`
2. Divide the remainder with 4 -> **`b/4`**
`4/4 = 1 (c is 1)`
3. Anchor day can be calculated with list above with YYYY and add a+b+c on the anchor day.
`2016 will be between 2000~2099, Tuesday.`
`a+b+c = 1 + 4 + 1 = 6`
`Now add result from 2 on Tuesday. Which will be Tuesday + 6 = Monday.`
`2016's doomsday is Monday`

---

## Calculate a given date
Now we know 2016's doomsday is on **Monday**. Then we can simply calculate the difference in date between doomsday and the day we want to know, to calculate the day.

Using the example above, 2016 03 24, we know 2016's doomsday is on Monday and I will use February 29th for my doomsday since it's a leap year.

Days until February 29th are 60 days and days until 24th of March is 84 days. Now we can calculate the day with the function I wrote on the program.

`dayOfWeek = ((doomsday + DAYS_PER_WEEK) - (DAYS_PER_WEEK + ((daysToEndOfFeb - daysToInputDay) % DAYS_PER_WEEK))) % DAYS_PER_WEEK;`

 This will give me a day of week with leap year case.

 `dayOfWeek = ((4 + 7) - (7 + ((60 - 84) % 7))) % 7;`
`                = ((11) - (7 + (-3))) % 7;`
`                = 7 % 7`
`                = 0`
`                = Thursday`

---

## Download sample C file
You can download sample C file from ***[HERE](https://github.com/augusdn/C-Programming/blob/master/doomsday.c)***
