---
title : "[OOP] 람다 함수 (Lambda Function)"
date : 2026-03-19 17:59:00 +0900
categories : [Dev / OOP]
tags : [cpp, lambda, function, oop]
comments : true
pin : true
---

## 람다 함수 (Lambda Function)

### **1. 람다 함수**
**람다 함수**란 이름이 없는 간단한 함수 객체를 의미한다.
주로 짧은 로직을 한 번만 실행할 때 사용한다.

<br/>

-----------------

<br/>

### **2. 기본 형태**
```cpp
[capture](parameters) -> return_type {
	function_body
};
```

#### **예시**
```cpp
auto add = [](int a, int b) {
	return a + b;
};

cout << add(3, 5);	// 8
```

<br/>

-----------------

<br/>

### **3. 캡처 (Capture)**
**캡처**란 람다 함수 밖에 있는 변수를 가져오는 방식이다.

#### **예시**
```cpp
int x = 10;

auto f = [x](){
	cout << x;
};

f();	// 10
```

| 문법 | 의미 |  
|------|------|  
| `[=]` | 모든 외부 변수 값을 복사 |  
| `[&]` | 모든 외부 변수를 참조 |  
| `[x]` | x만 값 복사 |  
| `[&x]` | x만 참조 |

<br/>

-----------------

<br/>

### **4. 예시**
#### **람다 함수 바로 호**
```cpp
[](int a){
	cout << a;
}(5);		// 5
```

#### **정렬 람다 함수**
```cpp
vector<int> v = {1, 2, 3, 4, 5};

sort(v.begin(), v.end(), [](int a, int b){return a < b});
```

<br/>

-----------------

<br/>
