---
title : "[OOP] String (C++ vs. C#)"
date : 2026-02-21 14:21:00 +0900
categories : [Dev / OOP]
tags : [cpp, string, stringbuilder, oop, csharp]
comments : true
pin : true
---

## String (C++ vs. C#)

### **1. String**
**String**란 **문자열**을 의미하는 데이터 타입이다.

<br/>

#### **예시**
```cpp
int main()
{
	string s = "문자열";

	cout << s;	// "문자열" 출력
}
```

<br/>

-----------------

<br/>

### **2. C++**

#### **가변 (Mutable)**
C++에서의 String은 가변 객체이기에 수정 및 추가 등 다양한 연산이 가능하다.

```cpp
string  s = "Hello";  
s[0] = 'J';		// "Jello"
s += " World!";		// "Jello World!"
```

<br/>

#### **내부 구조**
-   내부적으로 `char` 배열로 구현된다.
-   null 문자 (`\0`) 로 끝나는 C 스타일 문자열과 호환이 가능하다.
-   `c_str()`로 C 스타일 문자열로 반환할 수 있다.
```cpp
string  s = "Hello";  
const  char* c = s.c_str();
```

<br/>

#### **메모리 관리**
-   직접 new/delete를 할 수 있다.
-   복사 및 이동 생성자 존재한다.
-   성능 세밀하게 제어할 수 있다.

```cpp
string a = "Hi";
string b = a; 		// 복사
```

<br/>

-----------------

<br/>

### **3. C#**

#### **불변 (Immutable)**
C#에서의 String은 불변 객체이므로 문자열 수정에 많이 비용이 든다.

```csharp
string s = "Hello";
// 문자열 수정 시 새로운 string 객체를 만들어 복사
s += " World!";
```
문자열 수정이 많다면 비효율적이기 때문에 **StringBuilder**를 대신 사용한다.

<br/>

#### **StringBuilder**
내부적으로 char 버퍼로 사용하여 문자열을 수정한다.

```csharp
StringBuilder sb = new StringBuilder();
  
void Update()
{  
	sb.Clear();
	sb.Append("Score: ");
	sb.Append(score);
	textUI.text = sb.ToString();
}
```

<br/>

#### **내부 구조**
-   UTF-16 기반으로 구현된다.
-   완전한 객체 타입이다.
-   가비지 컬렉션이 메모리를 관리한다.

<br/>

#### **메모리 관리**
-   가비지 컬렉션이 자동으로 메모리를 관리한다.
-   참조 타입이다.
-   불변 객체이기에 누가 바꿀 위험이 없어 같은 메모리를 참조할 수 있다.

```csharp
string b = "Hi"; // 같은 메모리 참조 가능
```
