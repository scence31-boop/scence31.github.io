---
title: "[Frontend] Ajax, Axios - 비동기 통신"
date: 2026-01-17 17:00:00 +0900
categories: [Frontend, JavaScript]
tags: [ajax, axios, javascript, frontend]
---

웹 페이지를 새로고침하지 않고도 서버와 데이터를 주고받는 비동기 통신

### 비동기 통신이란?
서버에 데이터를 요청한 후, 응답을 기다리지 않고 다음 코드를 바로 실행하는 방식으로, 사용자 경험을 향상할 수 있음

### Ajax vs Axios

| 구분 | Ajax (jQuery) |  Axios (Library) |
| :--- | :--- | :--- |
| **특징** | jQuery 기반의 편리한 문법 | Promise 기반 라이브러리, `async/await`와 궁합이 좋음 |
| **JSON 변환** | 자동으로 처리됨 | 자동으로 처리됨 |
| **브라우저 호환** | 매우 높음 | 매우 높음 |
| **설치 여부** | jQuery 설치 필요 | 라이브러리 설치 필요 |

### 코드 예시

#### 1. Ajax (jQuery 방식)
```javascript
$.ajax({
    url: '/api/data',
    type: 'GET',
    success: function(result) {
        console.log(result);
    }
});
```

#### 2. Axios (await/async 사용)
```javascript
const getData = async () => {

    try {

        const result = await axios.get('/api/data');
        console.log(result.data);

    } catch (error) {

        console.error(error);
    }
};
```