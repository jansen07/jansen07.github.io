---
layout: post
title:  "Numeric Promotion Rules - OCA Review Notes"
description: "These are my notes on Numeric Promotion Rules during OCA review preparations"
date:   2018-09-25 10:00:00 +0800
categories: tutorial oca java chapter2
---

#### 4 Numeric Promotion Rules

Numeric Promotion Rules
1. If two values have different data types, Java will automatically promote one of the val-
ues to the larger of the two data types.
2. If one of the values is integral and the other is floating-point, Java will automatically
promote the integral value to the floating-point value’s data type.
3. Smaller data types, namely byte , short , and char , are first promoted to int any time
they’re used with a Java binary arithmetic operator, even if neither of the operands is int .
4. After all promotion has occurred and the operands have the same data type, the result-
ing value will have the same data type as its promoted operands.

##### Rule 1.

```java
	int num =1; // default int
	long longNum = 23L; // long Literal

	// rule 1 -> promote values to larger data type
	long imLong = num + longNum; 
```

*If same datatype -> resulting value will have same datatype.*

```java
	float num1= 2300000000F;
	float num2= 55000000000000F;
	float num3 = num1 * num2;
```

##### Rule 2.

*floating value and integral value operation promotion*
```java
	long longNum = 23; // integral
	float floatNum= 1000F; // floating
	//promote longNum value to floating point value's data type(float in this case).
	float z = longNum * floatNum; 
```


##### Rule 3.

```java
	byte byteNum= 5;
	short shortNum = 2;

	// both will be promoted to int first before the actual operation.
	int result = byteNum * shortNum; 
```
* even if you cast those datatype to short,byte,char it will still be promoted to int before performing operation. therefore return type will always be int. except adding parenthesis and cast


```java
	byte byteNum= 5;
	short shortNum = 2;
	
	// both will be promoted to int first before the actual operation.
	int result = (short)byteNum * (short)shortNum; 

	// compile time error lossy conversion
	short shortResult = (short)byteNum * (short)shortNum;
```

* cast if you want short data type *

```java
	byte byteNum= 5;
	short shortNum = 2;

	// after promotion to int and returning int. we can now cast it to short
	short result = (short) (byteNum * shortNum); 
```


##### Rule 4. ( after promotion of operands resulting value is same type.

* All samples above, the resulting value has same datatype with the variable declared on left side*
