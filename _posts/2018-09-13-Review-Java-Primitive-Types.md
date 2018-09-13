---
layout: post
title:  "Primitive Data Types OCA Review Notes"
description: "These are my notes on primitive data types during OCA review preparations"
date:   2018-09-13 16:10:00 +0800
categories: tutorial oca java chapter1 primitivedatatypes
---



The exam assumes you are well versed with this <i>8 datatypes</i> and their <i>relative sizes</i> and what can be stored in them.
```
java has 8 datatypes

```
byte -> -128 to 127

don't memorize the max. allowed or min.

you won't convert b/w number systems on the exam.

you can add _ underscores b/w numbers except begin/end same in decimal ex. _1_._1_


defaults
<br>numbers : int
<br>decimals : double

```java
int num = 1_234_567_890;
long longNum =  4_234_567_890L;
float f = 123.2f;
double d = 123.2;
```

cast or add litterals if initializing
<br>

Primitive types assign to null will give compile error

```java
int num=null;
long distance=null;
float money=null;
double savings=null;

```


