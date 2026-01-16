---
title: "[Oracle] Join 개념과 문법"
date: 2026-01-16 14:00:00 +0900
categories: [Database, Oracle]
tags: [oracle, sql, join, inner-join, outer-join, backend]
---

## 1. Join이란?
관련 있는 테이블들을 연결하여 하나의 결과를 만드는 작업

### 오라클 & ANSI
* **오라클 전용 구문**: `,`로 테이블을 나열하고 `WHERE`절에 조인 조건을 기술
* **ANSI 표준 구문**: `Join` 키워드와 `ON/USING` 구문을 사용

---

## 2. 조인 유형별 비교 및 예시

### 등가 조인(Equal Join) / 내부 조인(Inner Join)
연결고리 컬럼값이 **일치하는 행만** 조회함 (일치하지 않으면 제외)

* **오라클:** `WHERE E.DEPT_CODE = D.DEPT_ID`
* **ANSI:** `INNER JOIN DEPARTMENT D ON (E.DEPT_CODE = D.DEPT_ID)`
* **특이사항:** 컬럼명이 같을 경우 ANSI에서는 `USING (JOB_CODE)` 혹은 `NATURAL JOIN` 사용 가능



### 포괄 조인 / 외부 조인 (Outer Join)
일치하지 않는 행도 포함하여 조회하고 기준이 되는 테이블 방향(LEFT/RIGHT) 확인해야 함

| 종류 | 설명 | 오라클 특이점 |
| :--- | :--- | :--- |
| **LEFT OUTER** | 왼쪽 테이블 데이터는 무조건 포함 | `WHERE E.DEPT_CODE = D.DEPT_ID(+)` |
| **RIGHT OUTER** | 오른쪽 테이블 데이터는 무조건 포함 | `WHERE E.DEPT_CODE(+) = D.DEPT_ID` |
| **FULL OUTER** | 양쪽 테이블 데이터 모두 포함 | **오라클 전용 구문 사용 불가** |

### 비등가 조인 (Non-Equal Join)
`=`이 아닌 `BETWEEN`이나 비교 연산자를 사용
```sql
-- 급여 등급 매칭 예시
SELECT EMP_NAME, SALARY, SAL_LEVEL
  FROM EMPLOYEE
  JOIN SAL_GRADE ON (SALARY BETWEEN MIN_SAL AND MAX_SAL);
```

### 자체 조인 (Self Join)
한 테이블에 별칭(alias)을 사용해 다른 테이블인 것처럼 조인

```sql
SELECT E.EMP_NAME "사원", M.EMP_NAME "사수"
  FROM EMPLOYEE E
  LEFT JOIN EMPLOYEE M ON (E.MANAGER_ID = M.EMP_ID);
```
