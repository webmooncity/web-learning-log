# JavaScript review, Day 17
> Date : 2025-12-30-TUE

* 오늘 적어도 JavaScript 끝내자. 너무 진도가 늦다.

---

## 12.4, 노드 추가, 삭제하기

* DOM 트리는 여러 타입의 노드로 구성되지만, 주축이 되는 노드는 **요소 노드**

## 12.5, 폼 조작하기

## 12.6, 이벤트 다루기

* 이벤트(event)는 웹 브라우저와 사용자 사이에 상호작용이 발생하는 특정 시점을 의미. 이벤트가 발생하면 이벤트 종류에 따라 어떤 작업을 하거나 미리 등록한 함수를 호출하는 등의 조작을 자바스크립트로 지정 가능.

* 이벤트 등록 : 인라인, 프로퍼티 리스터, 이벤트 등록 메서드
  - 인라인
  - 프로퍼티 리스너(property listener) : 요소 노드에 직접 속성으로 이벤트를 등록하는 방법
  - 이벤트 등록 메서드 : 3가지 방법 중 가장 권장하는 방식
  ```javascript
  <노드>.addEventListener("<event type>", <event function>);
  ```
    - 이벤트 타입(event type, 위 예시의)은 이벤트 종류에서 on만 뺌
    - 함수 표현식으로 정의된 함수는 호이스팅에 의해 선언과 할당이 분리되므로 참조하려는 함수가 addEventListener() 메서드보다 반드시 위에 작성되어야 함.
    - 함수 선언문은 "함수 자체"가 호이스팅되고,<br>
      함수 표현식은 "변수만" 호이스팅되며 함수 값은 실행 시점에 할당됨.

- 1분 퀴즈
```javascript
<button>click<button>
<script>
    const btn = document.querySector("button")
    const clickEvent = () => {
        alert("button dblclick, Alert");
    }
    btn.addEventListener("dblclick", clickEvent)
<script>
```

---

## 12.7, 이벤트 객체와 this

* 이벤트 객체 : 이벤트 타입에 따라 발생하는 이벤트의 각종 정보가 들어 있는 객체 집합. 개발자가 직접 생성하는 것이 아니라 이벤트가 발생하면 실행되는 함수의 매개변수로 같이 전달됨.
- 이벤트 취소, preventDefault()

## Selfcheck

* JavaScript review completed.

---