---
title : "[OOP] 인스턴스 (Instance)"
date : 2026-02-22 12:25:00 +0900
categories : [Dev / OOP]
tags : [cpp, instance, oop, csharp]
comments : true
pin : true
---

## 인스턴스 (Instance)

### **1. 인스턴스 (Instance)**
**인스턴스**란 특정 클래스를 기반으로 생성된 구체적인 객체를 의미한다.
쉽게 말하자면 `클래스 = 설계도`이고, `인스턴스 = 그 설계도로 만든 건물`이다.

보통 프로그래밍에서는 **객체**와 **인스턴스**를 같은 단어로 생각한다.

#### **예시**
```cpp
// 클래스 (메모리 상에 위치하지 않는다.)
class  Dog
{  
public:  
  string name;  
};

// 인스턴스 (이때부터 메모리에 할당된다.)
Dog  myDog;
```

<br/>

-----------------

<br/>

### **2. 인스턴스화**
```cpp
Person  p1;
```
- 스택 영역에 생성된다.
- 함수 종료 시 자동으로 해제된다.

<br/>

```cpp
Person* p2 = new  Person();
```
- 힙 영역에 생성된다.
- 동적 할당이다.
- 반드시 delete가 필요하다.

<br/>

```cpp
public  GameObject  enemyPrefab;  
  
void  Start()  
{  
	Instantiate(enemyPrefab, new Vector3(0,0,0), Quaternion.identity);
}
```
- 유니티 프리팹 인스턴스화
- Monobehaviour에서는 new로 생성할 수 없다.

<br/>

-----------------

<br/>
