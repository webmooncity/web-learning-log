# JavaScript review, Day 16
> Date : 2025-12-29-MON

* 오늘 지금 복습하는 책의 JavaScript 파트를 다 끝내자. 될 수 있으면 끝까지 끝내고 싶다.
* 그리고 ChatGPT 조언에서 인상 깊었던 게 있다. 일단 실습을 하며 채워가자. 바로 GitPage 알아봐야겠다.

---

## 12.3, 노드 조작하기

- 컨텐츠 조작
- 스타일 조작
```javascript
<노드>.style.<css 속성명> = <속성값>;
```
* CSS 속성 중에서 background-color 속성과 같이 속성명에 대시(-)가 있는 속성은 JavaScript에서 -를 뺄셈 연산자(-)로 인식. 그러므로 backgroundColor처럼 카멜 표기법으로 변경해서 작성.

- 클래스 속성 조작

- 데이터 속성
  - 새로 추가된 data-* 속성 : HTML 문법에서 사용할 수 있는 속성 외에 사용자가 원하는 속성을 추가할 수 있게 한 사용자 정의(custom) 속성.

- 메서드로 속성 조작

