---
title : "[자료구조] 맵(Map)과 딕셔너리(Dictionary)"
date : 2026-01-28 20:13:00 +0900
categories : [Dev / CS]
tags : [computer, science, cpp, opp, map, hashmap, dictionary, hash, data, sturcture]
comments : true
pin : true
---

## 맵(Map) & 딕셔너리 (Dictionary)

### 1. 맵 (Map)
**맵**이란 키-값을 한 쌍으로 데이터를 저장하는 자료구조이다.
값은 중복이 가능하지만 키는 중복이 불가능하다.

C++(```std::map```)에서는 **이진 탐색 트리**로 구현되며 데이터가 순서대로 정렬된다.
평균적인 시간 복잡도는 $O(log n)$이다.

#### **맵의 사용 예시**
```cpp
#include <map>
#include <iostream>
using namespace std;

int main()
{
	// string으로 키 저장, int로 값 저장
    map<string, int> m;
    m["apple"] = 3;
    m["banana"] = 5;

    for (auto& p : m)
    {
        cout << p.first << " " << p.second << endl;
    }
}
```

<br/>

-----------------

<br/>

### **2. 해시맵 (HashMap)**
**해시맵**이란 맵을 구체적으로 구현한 자료구조이다.
내부적으로 **해시 함수**를 사용하는 맵을 의미한다.

C++(```std::unordered_map```)에서는 **해시 테이블**로 구현되면 데이터가 정렬되지 않는다.
검색, 삭제, 삽입에 걸리는 평균적인 시간 복잡도는 $O(1)$이다.
충돌이 많을 경우 $O(n)$이 걸릴 수도 있다.

#### **해시맵 사용 예시**
```cpp
#include <unordered_map>
#include <iostream>
using namespace std;

int main()
{
	// string으로 키 저장, int로 값 저장
    unordered_map<string, int> um;
    um["apple"] = 3;
    um["banana"] = 5;

    cout << um["apple"] << endl;
}
```

<br/>

-----------------

<br/>

### **3. 딕셔너리 (Dictionary)**
**딕셔너리**란 맵의 또 다른 이름이다.
같은 맵의 개념이지만 프로그래밍 언어에 따라 맵, 해시맵, 딕셔너리 등 부르는 이름이 다양하다.
**유니티**에서는 딕셔너리를 사용한다.

#### **예시**
```cpp
using System.Collections.Generic;

Dictionary<string, int> scoreMap = new Dictionary<string, int>();

scoreMap["Wolf"] = 10;
scoreMap["Player"] = 100;
```

<br/>

-----------------

<br/>
