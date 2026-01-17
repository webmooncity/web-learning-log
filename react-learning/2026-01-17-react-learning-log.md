# React learning, Day 02
Date : 2026-01-17 Saturday

---

# 2장, JSX 개요

- JSX(JavaScript XML)

## 2.1, JSX란

* JSX(JavaScript XML) : 자바스크립트 코드 안에서 HTML과 비슷한 문법을 사용해 UI를 정의할 수 있도록 도와주는 **문법 확장(syntactic extension)**
- 쉽게 말해, 자바스크립트 안에서 HTML처럼 생긴 코드를 쓸 수 있게 해주는 문법.

## 2.2, JSX의 문법적 특징

* JSX로 작성된 컴포넌트는 반드시 하나의 태그(요소)만 반환해야 함.

- 프래그먼트(Fragment) : 여러 요소를 하나로 묶어주는 가상의 태그
- 기본문법
  ```JSX
  <React.Fragment>
    <div>첫 번째 영역</div>
    <div>두 번째 영역</div>
  <React.Fragment>
  ```
- 단축 문법 : 실무에서는 단축 문법을 더 자주 사용.
  ```jsx
  <>
    <div>첫 번째 영역</div>
    <div>두 번째 영역</div>
  </>
  ```

* JSX에서는 빈태그(self-closing tag)라도 `<br />`처럼 자체 종료 태그(self-closing tag)를 사용해야 함.
* 태그 속성은 카멜 케이스로 작성 : JSX에서는 속성명을 자바스크립트 변수명처럼 카멜 케이스로 작성.
- 몇 가지 속성이 자바스크립트 예약어와 충돌할 수 있음. class -> className

* 표현식은 중괄호 안에서 사용 : JSX에서는 중괄호({}) 안에 **자바스크립트 표현식**을 넣어 사용할 수 있음.
* 인라인 스타일은 객체로 지정 : JSX에서는 style 속성에 문자열이 아닌 자바스크립트 객체를 할당함. 그리고 CSS 속성명은 반드시 카멜 케이스로 작성해야 함.
- 이중 중괄호. 바깥 {}의 의미 : JS 표현식 시작. 안쪽 {}의 의미 : 객체 리터럴.

* JSX에서는 중괄호 안에 `/* 주석 내용 */` 형태로 주석(comment)를 작성해야 함.

---