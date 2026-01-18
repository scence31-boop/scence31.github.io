---
title: "[Backend] JSP와 Servlet"
date: 2026-01-18 14:00:00 +0900
categories: [Backend, Java]
tags: [jsp, servlet, java, mvc, backend]
---

자바 서버 페이지(JSP)는 HTML 코드 안에 자바 코드를 포함하여 웹 브라우저에 동적인 콘텐츠를 전달하는 언어다

### JSP?
- **Servlet 기반:** JSP는 실행할 때 서블릿(Servlet)이라는 자바 파일로 변환되고 컴파일된다. 자바가 뿌리임.
- **동적 콘텐츠 생성:** 고정된 HTML에 DB에서 가져온 데이터(DTO)를 결합하여 화면을 보여줌
- **문법:** 스크립틀릿(`<% %>`)도 있지만 더 편리한 방식의 **EL**과 **JSTL**을 주로 사용



### MVC 패턴에서의 역할
프로젝트 진행 시 **MVC(Model-View-Controller) 패턴**을 적용했음
- **Model:** DTO와 DAO로 데이터 처리
- **View (JSP):** 사용자에게 보여지는 화면(비즈니스 로직 제외)
- **Controller (Servlet):** 사용자의 요청을 받아 모델과 뷰를 연결

### 내장 객체
- 필요한 객체 `request`, `response`, `session` 등을 별도로 선언하지 않고 바로 사용
