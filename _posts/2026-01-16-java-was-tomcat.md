---
title: "[WAS] Apache Tomcat 특징과 구성 요소"
date: 2026-01-16 14:00:00 +0900
categories: [WAS, Java]
tags: [tomcat, was, backend, java, server]
---

Apache Tomcat은 클라이언트의 요청을 수신하고 Engine/Host/Context 구조로 요청을 분기한 뒤, Thread 기반으로 Servlet을 실행하여 응답을 생성하는 구조를 가진 WAS

### 1. Apache Tomcat 특징

1. **Java 기반 WAS:** Java 웹 애플리케이션 실행을 위한 환경을 제공한다. 클라이언트의 HTTP 요청을 받아 비즈니스 로직을 실행하고 동적인 응답을 생성한다.
2. **Servlet/JSP 컨테이너:** Servlet과 JSP 중심의 웹 계층에 특화되어 있으며, Spring Framework 환경에서 자주 사용된다.
3. **경량성 및 단순한 설정:** 타 WAS 대비 구조가 가벼워 운영 부담이 낮으며, 중소규모 서비스 및 SaaS 환경에 적합하다.
4. **Thread Pool 방식:** 요청당 스레드를 할당하여 다수의 동시 요청을 효율적으로 처리한다.
5. **웹 서버 연동 최적화:** Nginx나 Apache HTTP Server와 연동하여 사용하며, 웹 서버는 정적 리소스 처리를, Tomcat은 애플리케이션 로직 실행을 담당한다.
   - 구조: Client -> Web Server -> Tomcat -> Database

### 2. 구성 요소

1. **Connector:** 클라이언트의 HTTP 요청을 수신하는 통신 창구로 포트, 프로토콜, 타임아웃 등을 설정하며 수신한 요청을 Tomcat 내부 엔진으로 전달한다.
2. **Container 구조:** 요청을 처리하는 계층적 구조를 가진다.
   - **Engine:** 요청 처리를 담당하는 최상위 엔진
   - **Host:** 하나의 도메인(가상 호스트) 단위를 담당
   - **Context:** 개별 웹 애플리케이션 단위의 설정과 실행을 관리
3. **Thread Pool:** 요청 처리를 담당하는 실행 단위로 하나의 요청에 하나의 스레드를 배정하여 병렬 처리를 가능하게 한다.
4. **Servlet / JSP:** 실질적인 비즈니스 로직을 수행한다. DB 연동을 처리하고 HTML 또는 JSON 형태의 결과물을 생성한다.
5. **주요 설정 파일:**
   - **server.xml:** 전체 서버 구조, 포트 번호, 커넥터 설정 등 담당
   - **context.xml:** 개별 애플리케이션별 환경 변수나 DB 커넥션 풀(DBCP) 등 설정
   - **web.xml:** 웹 애플리케이션의 배치 기술서로, URL과 Servlet 매핑 등 정의