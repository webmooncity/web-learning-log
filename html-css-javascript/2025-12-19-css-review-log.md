# CSS review, Day 06
> Date : 2025-12-19-FRI

---

## 6.7 애니메이션 속성으로 전환 효과 제어

- 애니메이션(animation) 속성의 주요 문법 구성 : 스타일 속성과 키 프레임(@keyframes)
- 키 프레임(@keyframes) : 키 프레임에는 시작과 종료에 해당하는 최소 2개 시점에 대한 스타일이 정의되어야 함.
- 형식
  ```css
  @keyframes <키 프레임명>{
    0%{/* CSS code */}
    n%{/* CSS code */}
    100%{/* CSS code */}
  }
  ```
* 애니메이션은 키 프레임, animation-name 속성, animation-duration 속성만 있으면 전화 효과를 적용할 수 있음.
* 그러나 3가지 중 하나라도 빠지면 전환 효과는 적용되지 않음.

* @(at-rule) : @로 시작하는 모든 문법을 At-rule이라고 부름.
* 메타 레벨(Meta-level)이란? 메타(meta)란, 대상을 직접 다루는 것이 아니라 그 대상을 다루는 '규칙 자체'를 다루는 것
* At-rule의 본질: 이건 선택자 기반 스타일이 아니다. CSS 자체에게 주는 지시문이다.
* At-rule : 구조가 규칙마다 다름. <br>
  대상 : CSS 엔진 <br>
  목적 : CSS 동작 제어 / 규칙 정의
* CSS는 두 층위가 있다. 스타일 레벨, 메타 레벨.

## 6.8 변형 효과 적용

## 6.9 웹 폰트와 아이콘 폰트 사용

- web font, icon font
- CDN(Content Delivery Network)

## 6장 마무리

## Selfcheck 읽기(읽다가 건너뜀)

---
