---
title : "[OOP] Call by Value & Call by Reference"
date : 2026-02-24 15:06:00 +0900
categories : [Dev / OOP]
tags : [cpp, pointer, reference, oop, csharp]
comments : true
pin : true
---

## Call by Value & Call by Reference

### **1. Call by Value (값에 의한 호출)**
**Call by Value**란 함수에 **값**을 복사해서 전달하는 방식을 말한다.
즉, 변수의 원본이 아닌 **복사본**을 함수에 넘기는 것이다.

<br/>

![Desktop View](/assets/img/value.jpg){: w="600" h="300" }

<br/>

#### **예시**
```cpp
void change(int x)
{
	x = 100;	// 함수가 끝나면 x의 메모는 사라진다.
}

int main()
{
	int a = 10;
	change(a);
	
	cout << a;	// 10 (복사해서 전달했기에 값이 바뀌지 않는다.)

	return 0;
}
```

<br/>

-----------------

<br/>

### **2. Call by Reference (참조에 의한 호출)**
**Call by Reference**란 함수에 참조를 전달하는 것을 말한다.
즉, 원본 변수를 참조로 선언하여 함수에 전달하는 방식이다.

#### **예시**
```cpp
void change(int& x)
{
	x = 100;
}

int main()
{
	int a = 10;
	change(a);

	cout << a;	// 100 (원본을 전달했기 때문에 값이 바뀐다.)

	return 0;
}
```

<br/>

#### **포인터를 사용하는 방식**
Call by Reference는 포인터를 사용해 매개변수를 전달하는 방식과 유사하지만 문법이 다르다.
참조로 전달하는 것이 간단하다.

```cpp
void change(int* x)
{
	*x = 100;
}

int main()
{
	int a = 10;
	change(&a);

	cout << a;	// 100

	return 0;
}
```

<br/>

-----------------

<br/>
