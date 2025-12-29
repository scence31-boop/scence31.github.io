---
title: "[Java] API 활용과 String 클래스"
date: 2025-12-29 17:00:00 +0900
categories: [Backend, Java]
tags: [java, api, string, stringpool, wrapper]
---

## 자바 API
API: 자바에서 미리 만들어 제공하는 프로그래밍 도구 모음

* **특징**: `import` 구문 없이도 바로 사용할 수 있음
* **주요 클래스**: `Object`, `String`, `Math`, `System` 등 자바의 뼈대가 되는 클래스

---

## String 클래스: 불변성(Immutable)
자바에서 String은 일반적인 객체와 다르게 작동함. 변하지 않는다는 특징이 있음

### String Pool (상수풀)
문자열 리터럴 `"abc"`를 생성하면 Heap 영역 내부의 상수풀(String Pool)에 저장됨
- 같은 문자열을 또 만들면 새로 생성하지 않고 기존 주소를 재사용 (메모리 절약)
- 하지만 `new String("abc")`로 만들면 무조건 새로운 객체가 생성되니 주의


### String은 왜 불변일까?
한 번 만든 문자열을 수정하면, 기존 값이 바뀌는 게 아니라 새로운 주소에 수정된 문자열이 생긴다. - 값이 자주 바뀌는 상황에서 + 연산자로 문자열을 합치면 쓰레기(Garbage) 객체가 많이 생겨 성능이 떨어진다.

---

## StringBuilder & StringBuffer
문자열을 자주 변경(추가, 삭제, 수정)해야 할 때는 String 대신 가변성을 가진 클래스를 써야 함

* **StringBuilder**: 속도가 매우 빠름 (단일 쓰레드)
* **StringBuffer**: 멀티 쓰레드 환경에서 안전

```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World"); // 기존 객체 안의 값이 직접 변함!
System.out.println(sb.toString());
```

## Wrapper 클래스와 Auto Boxing
기본 자료형(Primitive Type)을 객체로 다뤄야 할 때 사용하는 클래스. 자바는 8개의 기본 타입을 각각 대응하는 객체 형태의 클래스로 제공

* **기본 타입과 대응하는 Wrapper 클래스**
    - `int` → `Integer`, `char` → `Character`
    - `double` → `Double`, `boolean` → `Boolean` 등 (첫 글자가 대문자로 시작!)

### Boxing & Unboxing
* **Boxing**: 기본 자료형을 객체(Wrapper)로 만드는 것
* **Unboxing**: 객체(Wrapper)에 담긴 값을 기본 자료형으로 꺼내는 것
* **Auto Boxing/Unboxing**: 자바가 자동으로 변환을 처리해 줌. 덕분에 우리는 타입 고민 없이 편리하게 코드를 짤 수 있다.

```java
Integer num = 10; // Auto Boxing (int -> Integer)
int n = num;      // Auto Unboxing (Integer -> int)

// 활용 예시: 리스트에는 객체만 담길 수 있지만, 자동 박싱 덕분에 int를 바로 넣을 수 있음
List<Integer> list = new ArrayList<>();
list.add(100);
```