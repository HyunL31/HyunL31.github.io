---
title : "[Unity] MonoBehaviour"
date : 2026-01-16 16:33:00 +0900
categories : [Game / Unity]
tags : [unity, game, dev]
comments : true
pin : true
---

## MonoBehaviour

유니티에서 **MonoBehaviour**이란 게임 오브젝트에 붙어 동작을 실행시키는 기본 스크립트 클래스이다.
C# 스크립트를 MonoBehaviour로 만들면 유니티 생명주기 메서드들을 자동으로 호출해주고, Inspector 변수 노출, 컴포넌트, 코루틴 등을 사용할 수 있다.

##### **예시**
```cpp
using UnityEngine;

public class PlayerMover : MonoBehaviour
{
    void Update()
    {
	    // 생명주기 메서
    }
}
```

#### **MonoBehaviour가 아닌 클래스**

MonoBehaviour가 아닌 클래스는 유니티의 컴포넌트 시스템과 직접적인 연동이 불가능하다.
그러나 이러한 클래스는 MonoBehaviour를 상속받은 클래스에서 인스턴스화하여 사용할 수 있다.
주로 데이터 관리 등에 사용된다.

##### **예시**
```cpp
public class PlayerData
{
    public int hp;
    public int attack;
}
```

<br/>

-----------------
