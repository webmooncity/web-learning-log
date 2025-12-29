# JavaScript review, Day 15
> Date : 2025-12-28-SUN

* 이틀 간, 그동안 너무 신경 과부하였는지, 푹 잤다. 오늘부터 정진하자. 너무 개운한데, 무리하지 말고, 이 리듬을 살리자.
* 시작이 어렵다. 작게나마라도 시작하면, 그 다음부터 공부는 흐름이다.
* 내일 아마 javascript review 1회가 끝날 것 같다. 프로젝트 웹 개발 예제 한 번 얼른 끝내고, React 넘어가자.

---

## 11.3, 표준 내장 객체 사용하기

* 표준 내장 객체(standard built-in object) : 자바스크립트에 기본으로 내장된 객체
- String 객체
- Array 객체 : 기본 자료형 중 배열을 다루는 객체
- Date 객체
- 주의점, 월은 9부터 시작
- Math 객체

```javascript
function getMinMaxRandom(min, max){
    return Math.floor(Math.random() * (max - min)) + 1 + min;
}
const maxRandom = getMinMaxRandom(10, 20);
console.log(maxRandom);
```
- 위 부분 책 내용이 잘못됨.
- off-by-one 오류 : '1 차이'에서 생기는 경계 실수이며, 배열·반복문·랜덤에서 가장 흔하고 가장 위험한 논리 오류.
- 시작은 포함, 끝은 미포함 `for(let i = start; i<end; i++){...}`

- 1분 퀴즈
```javascript
const arr = [10, 120, 30, 50, 20];
arr.sort((a,b)=>b-a);
console.log(arr[0]);
```

---

## 11.4, 브라우저 객체 모델 사용하기

* 브라우저 객체 모델(BOM, Browser Object Model) : 자바스크립트 언어 사양에 포함되지 않고, 웹 브라우저에서 제공하는 객체.

## Selfcheck

### 02
- 나의 답
```javascript
<body>
    <button onclick="openGoogle()">구글</button>
    <script>
        openGoogle(){
            widow.open('http://www.google.com', 'google01','width=500, height=300')
        }

    </script>
</body>
```

- 답지
```javascript
<body>
  <button onclick="popup()">팝업</button>
  <script>
    function popup(){
      const left = (screen.availWidth - 500) / 2 + window.screenX;
      const top = (screen.availHeight - 300) / 2;
      window.open('https://google.com', 'popup', 'width=500, height=300, left=' + left + ', top=' + top);
      console.log(window.screenX);
    }
  </script>
</body>
```
- 답지 이해 완료.

---

## 12장, 문서 객체 모델과 이벤트 다루기
* 문서 객체 모델(DOM, Document Object Model)


## 12.1, 문서 객체 모델 이해하기

* 웹 브라우저는 생성한 문서 객체 모델(DOM)을 통해 HTML 문서의 구성 요소를 객체로 인식
* 자바스크립트도 웹 브라우저의 문서 객체 모델(DOM)을 조작해 웹 브라우저에 표시되는 HTML 문서 구조를 변경하거나 새로운 구성 요소를 추가하는 등의 작업을 할 수 있음.

## 12.2, 노드 선택하기

* 자바스크립트는 주로 요소 노드를 선택해 조작.

### CSS 선택자 사용하기 - query 메서드

- querySelector(<CSS 선택자>)
- querySelectorAll(<CSS 선택자>)

* query 메서드는 매개변수로 CSS 선택자를 전달받기 때문에 get 메서드보다 범용성이 더 좋음.
* 이론적으로 메서드의 성능은 단순하게 특정 매개변수만 전달받는 get 메서드가 query 메서드보다 더 좋음. 그러나 현대적인 웹에서는 신경 쓰지 않아도 될 정도의 차이이므로 query 메서드를 사용하는 것이 나음.

---

## 12.3, 노드 조작하기