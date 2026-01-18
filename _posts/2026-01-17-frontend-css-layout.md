---
title: "[Frontend] CSS"
date: 2026-01-17 15:00:00 +0900
categories: [Frontend, CSS]
tags: [css, frontend, style]
---

CSS(Cascading Style Sheets)는 HTML 문서의 디자인과 레이아웃을 설정하는 언어다

### 1. CSS 선택자 우선순위
동일한 요소에 여러 스타일이 적용될 때, 아래의 우선순위에 따라 결정된다

1. **!important:** 최우선 적용 (남발 금지)
2. **Inline 스타일:** HTML 태그 안에 직접 작성 `style="..."`
3. **ID 선택자:** `#id`
4. **Class 선택자:** `.class`
5. **태그 선택자:** `div`, `h1`
6. **상속:** 부모 요소의 스타일을 물려받음

### 2. 박스 모델
HTML 요소는 사각형의 박스 형태다
- **Content:** 실제 내용 영역
- **Padding:** 테두리와 실제 내용 사이의 안쪽 여백
- **Border:** 테두리
- **Margin:** 요소와 요소 사이의 바깥쪽 여백



### 3. Flexbox 레이아웃
행 또는 열을 기준으로 요소를 배치하는 1차원 방식
- **`display: flex;`**: 부모 요소를 기준으로 잡음
- **`justify-content`**: 기준 방향 정렬 (center)



### 4. 반응형 웹 디자인
모바일, PC 모두에 최적화된 화면 제공

```css
/* 화면이 700px 이하일 때 적용 - 모바일 */
@media screen and (max-width: 700px) {
  .container {
    flex-direction: column;
  }
}
```