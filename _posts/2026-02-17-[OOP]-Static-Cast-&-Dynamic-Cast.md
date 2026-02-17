---
title : "[OOP] Static Cast & Dynamic Cast"
date : 2026-02-17 14:08:00 +0900
categories : [Dev / OOP]
tags : [cpp, class, struct, oop, csharp]
comments : true
pin : true
---

## Static Cast & Dynamic Cast

### **1. Cast란?**
**캐스트**란 어떤 자료형을 다른 자료형을 바꾸는 형변환을 의미한다.

<br/>

-----------------

<br/>

### **2. Static Cast**

#### **Static Cast란?**
**Static Cast**란 컴파일 타임에 자료형을 확인하는 캐스팅 방식이다.
런타임에 따로 검사를 하지 않기 때문에 위험할 수 있다.
따라서 형변환을 확신할 수 있을 때 주로 사용한다.

#### **Static Cast 특징**
- 컴파일 타임에 자료형을 확인한다.
- 캐스팅에 실패해도 ```nullptr``` 등을 반환하지 않는다.
- 런타임에 검사를 하지 않기 때문에 속도가 빠르다.

#### **예시**
```cpp
// 일반적인 수치 형변환
double x = 3.14;
int a = static_cast<int>(x); // 3, 명시적 형변환
```
```cpp
// 업 캐스팅 (안전)
struct Base { };
struct Derived : Base { };

Derived d;
Base* b = static_cast<Base*>(&d);
```
```cpp
// 다운 캐스팅 (위험)
struct Base { virtual ~Base() = default; };
struct Derived : Base { void only() {} };
struct Other : Base { };

Base* b = new Other();

Derived* d = static_cast<Derived*>(b);
d->only(); // 런타임에 오류가 생길 가능성이 있다.
```

<br/>

-----------------

<br/>

### **3. Dynamic Cast**
#### **Dynamic Cast란?**
**Dynamic Cast**란 런타임에 자료형을 확인하는 형변환 방식이다.
반드시 기반 클래스에 virtual 함수가 하나 이상 있어야 한다.

#### **Dynamic Cast 특징**
- 런타임에 자료형을 확인한다.
- 다형적 클래스 (virtual 함수)에서만 사용할 수 있다.
- Static Cast보다 안전하지만 느리고 비용이 있다.

#### **virtual 함수가 있어야 하는 이유**
- virtual 함수는 vtable을 생성한다.
- vtable에서 런타임 타입 정보를 확인할 수 있다.
- 따라서 virtual 함수가 있어야 Dynamic Cast가 가능하다.

#### **예시**
```cpp
struct Base { virtual ~Base() = default; };
struct Derived : Base { void only() {} };
struct Other : Base {};

Base* b = new Other();

Derived* d = dynamic_cast<Derived*>(b);

if (d)
{
    d->only();
}
else
{
    // b는 Derived가 아님
    // 캐스팅 실패
}
```
