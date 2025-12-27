# JavaScript review, Day 12
> Date : 2025-12-25-THU

* 어제는 어쩌다 보니, 잠을 푹 자고 쉬었다. 푹 쉬었으니, 오늘은 공부를 많이 나아가보자.

---

## 10.3, 함수 기능 확장하기

- 매개변수(parameter), 인수(argument)
- parameter : 함수를 정의할 때 외부에서 전달하는 데이터를 함수에서 받을 수 있도록 정의하는 변수
- argument :  정의한 함수를 호출할 대 소괄호 안에 전달하고 싶은 데이터를 적는데, 이를 인수라고 함.
* 매개변수도  함수 호출 시 데이터를 전달하지 않으면 undefined 값이 할당되어 코드를 실행해도 오류가 발생하지 않음.
- result 문 
- return 문은 데이터를 반환하지 않으면 단순히 함수 실행을 종료하는 역할만 하게 됨.

- return; : 함수 즉시 종료 + undefined 반환
- return 값; : 함수 즉시 종료 + 값 반환

* 1분 퀴즈, 2번

- 오답 수정 후<br>
```javascript
function getArrayMaxNumber(arr){
  let max = arr[0];
  for(let i = 1; i < arr.length; i++){
      if(arr[i] > max){
          max = arr[i];
      }
  }
  return max;
}
const max = getArrayMaxNumber([10, 50, 30, 63, 22]);
console.log(max);
```

---

## 10.4, 함수의 특징 이해하기

### scope
- 'function scope' vs 'block scope'
- 'global scope' vs 'local scope'
- 전역 스코프(global scope)에 선언한 변수를 ***전역 변수***, 지역 스코프(local scope)에 선언한 변수를 ***지역 변수***라고 함.
* 전역 스코프와 지역 스코프에 같은 식별자를 가지는 참조 대상이 있다면, 먼저 같은 지역 스코프의 식별자를 참조함. 그리고 같은 지역 스코프에서 참조할 식별자를 찾지 못할 때만 전역 스코프에서 찾음.

### 함수 호이스팅
- 호이스팅은 코드를 선언과 할당으로 분리해 선언부를 자신의 스코프 최상위로 끌어올리는 것을 말함.
- let과 const 키워드로 선언한 변수에는 적용되지 않음.
- 함수 선언문으로 정의된 함수는 호이스팅에서 선언부로 봄.
- 함수 표현식과 화살표 함수 방식으로 정의된 함수는 let이나 const 키워드로 선언했다면 호이스팅 자체가 되지 않음.

## 즉시 실행 함수 사용하기
- 즉시 실행 함수(IIFE, Immediately Invoked Function Expression)
- 함수를 정의하면서 동시에 실행까지 하는 함수.
- 형식
```javascript
(function(){})();
```
- 예
```javascript
(function init(){
    console.log("initialized!");
})();
```

---

selfchek

1. 
```
function circleCal(r){
    let area = r * r * 3.14
    return area;
}
let circleArea01 = circleCal(10);
let circleArea02 = circleCal(6); 
console.log(circleArea01);
console.log(circleArea02);
```

2. 
```javascript
function arrayMax(arr){
    let max = 0;
    for(i=0; i<arr.length; i++){
        if(max < arr[i]){
            max = arr[i];
        }
    }
    return max;
}
console.log(arrayMax([1,3,2,4,5,9,31,20]));
```

3. 
체질량 지수(BMI) = 몸무게 / 키(m)**2

```javascript
function calBmi(height, weight){
    let bmi = weight/((height/100)**2);
    if(bmi>=26){
        console.log(`${bmi}:비만`)
    }else if(bmi>=24){
        console.log(`${bmi}:과체중`)
    }else if(bmi>=18.5){
        console.log(`${bmi}:정상`)
    }else{
        console.log(`${bmi}:저체중`)
    }
    return;
}
calBmi(174, 85);
calBmi(174, 75);
calBmi(174, 72);
calBmi(174, 65);
```

---

## 11장, 자바스크립트 객체 다루기

## 11.1, 객체란?

* 객체? ***키(key)와 값(value)으로 구성된 속성의 집합***

### 객체 속성 다루기

- 대괄호 연산자로 접근하기
- 마침표 연산자
* 이미 만들어진 객체에 나중에 속성을 추가하는 것을 자바스크립트에서는 **속성을 동적으로 추가한다**고 합니다.
- 객체 자료형의 특성인 ***참조(reference)***
* 복사한 값을 재할당할 때 한쪽 데이터가 변경되어도 서로 영향을 미치지 않게 복사되는 것을 ***깊은 복사(deep copy)***라고 함.
* 기본 자료형과 다르게 객체와 같은 참조 자료형은 변수 공간에 데이터가 할당되는 것이 아니고, 데이터가 위치하고 있는 메모리의 주소 값만 할당됨. 자바스크립트에서는 이를 ***참조한다***고 표현함.
* 데이터를 복사했을 때 한쪽 데이터가 변경되면 다른 쪽 데이터도 변경되어 서로 영향을 받는 것을 ***얕은 복사(shallow copy)라고 함.

## 11.3, 표준 내장 객체 사용하기

* ***표준 내장 객체(standard built-in object)*** : 자바스크립트에 기본으로 내장된 객체