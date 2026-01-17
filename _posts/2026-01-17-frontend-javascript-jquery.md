---
title: "[Frontend] JavaScript ES6+, jQuery"
date: 2026-01-17 16:00:00 +0900
categories: [Frontend, JavaScript]
tags: [javascript, jquery, es6, frontend, dom]
---

프론트엔드의 꽃 JavaScript와 최신 ES6+ 문법, DOM, 그리고 효율성을 높여주는 jQuery

### DOM (document 객체)
DOM(Document Object Model)은 브라우저가 HTML 문서를 트리 구조로 표현한 것이며, `document` 객체는 이 구조에 접근하는 문이다

- **요소 선택:** `document.querySelector('.class')`, `document.getElementById('id')` 등
- **내용 변경:** `element.textContent`로 텍스트를 수정하거나, `element.style`로 디자인을 직접 제어
- **이벤트 바인딩:** `addEventListener('click', callback)`를 통해 사용자의 상호작용을 처리



### jQuery
JavaScript 문법을 편리하게 사용할 수 있게 해주는 라이브러리로, React 보다는 JSP에서 DOM 조작과 Ajax 통신 시 주로 사용함

| 구분 | JavaScript | jQuery |
| :--- | :--- | :--- |
| **요소 선택** | `document.querySelector('#btn')` | `$('#btn')` |
| **텍스트 변경** | `.textContent = '안녕'` | `.text('안녕')` |
| **이벤트 처리** | `.addEventListener('click', ...)` | `.on('click', ...)` |
| **스타일 변경** | `.style.display = 'none'` | `.hide()` |

- **이벤트 위임:** 동적인 요소에 이벤트를 걸 때 `$(document).on('click', '.target', function() { ... })` 형식을 사용해서 한번에 관리 가능함!

### ES6+ 최신 문법
리액트처럼 현대적인 프레임워크 사용할 때 필요함

- **변수 선언:** 기존 `var`는 지양하고 `let`과 `const`를 사용
- **화살표 함수:** `() => { ... }` 형태로 함수를 간결하게 선언
- **구조 분해 할당:** 객체나 배열의 값을 추출
- **템플릿 리터럴:** 백틱(`` ` ``)과 `${}`를 사용하여 문자열과 변수를 조합
- **전개 연산자 (Spread):** `...`을 사용하여 배열, 객체를 복사

#### var / let / const 비교

| 구분 | var | let | const |
| :--- | :--- | :--- | :--- |
| **스코프** | 함수 스코프 | 블록 스코프 | 블록 스코프 |
| **호이스팅** | O ( `undefined` ) | O ( TDZ ) | O ( TDZ ) |
| **재선언** | O | X | X |
| **재할당** | O | O | X |
| **전역 객체** | window에 등록 | X | X |
| **실무 사용** | X 지양 | O | O (기본) |