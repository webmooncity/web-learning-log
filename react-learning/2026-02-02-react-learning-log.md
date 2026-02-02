# React learning, Day 18 (실제: Day 10)
Date : 2026-02-02 Monday

---

## 8.2, 폼 제어하기

- 이전에 공부한 4장의 useState 훅과 useReducer 훅 읽기.

---

## 4.1, 컴포넌트의 상태란?

* **컴포넌트의 상태**(state)란 리액트 컴포넌트 내부에서 관리하는 데이터로, 사용자와의 상호작용에 따라 변경될 수 있는 값을 의미함.

## 4.2, useState 훅: 기본 상태 관리

* **훅**(hook)이란 함수형 컴포넌트에서 상태(state)와 생명주기(lifecycle)을 쉽게 관리할 수 있도록 도와주는, 리액트에서 제공하는 특별한 함수.

- 구조 분해 할당(Destructuring assignment): 객체(object)나 배열(array) 안에 들어있는 값을 "꺼내서" 변수에 한 번에 담는 문법.

* useState 훅
  - 형식 `const [state, setStete] = useState<Type>(initialState);`

* 제네릭 타입
  - **제네릭**(generic): 타입스크립트에서는 특정 타입에 고정되지 않고, 다양한 타입에서 재사용할 수 있는 기능인 제네릭을 제공.
  - 제네릭을 사용하면 같은 함수 코드를 다양한 타입에 유연하게 재사용 할 수 있음.
  - 또한, 타입스크립트의 장점인 **타입 안정성**(type safety)도 유지할 수 있음.

* 콜백 함수(callback function): 나중에 실행해 달라고 다른 함수에 넘겨주는 함수.

* 상태 변경 함수에 콜백 함수를 넘겨 주는 이유: **리액트의 상태 업데이트 방식 때문**
  - 리액트는 여러 상태 변경을 즉시 처리하지 않고 비동기적으로 처리해 렌더링이 끝난 뒤 한 번에 모아서 적용함.
  - 이 방식을 **일괄 업데이트**(batch update)라고 하며, 불필요한 리렌더링을 줄여 성능을 최적화하는 방식.
  - 이 문제는 상태 병경 함수에 **콜백 함수** 형태를 사용하면 해결할 수 있음.

* 리액트 훅의 호출 위치: 반드시 함수형 컴포넌트 내부의 최상위에서 호출해야 함.
  - 여기서 **최상위**(top-level)란 컴포넌트 함수 내부에서 조건문(if), 반복문(for), 함수 정의, 이벤트 핸들러 등 어떤 블록 안에도 포함되지 않은 영역을 뜻함.

- **훅의 규칙**(rules of hooks): 리액트 공식 문서에서는 리액트 훅을 사용할 때 반드시 지켜야 하는 규칙들을 훅의 규칙으로 정의.

* ***다시 복습을 하니, 이전에는 안개 같이 흐릿했던 내용이 환해진다. 신기할 정도로 1회독과 지금 복습의 2회독의 선명함이 다르다.***

---

## 4.3, useReducer 훅: 복잡한 상태 관리

* useReducer 훅 기본 문법
  - 형식 `const [state, dispatch] = useReducer<Type>(reducer, initialState);`
  - reducer: **리듀서 함수**(reducer function)는 상태를 변경하는 함수로, 이전 상태와 액션을 받아서 새로운 상태를 반환함.
  - dispatch: **액션 발생 함수**(dispatch function)
  - **액션**(action): 리듀서 함수에서 어떤 상태 변경을 수행할지 결정하기 위해 참조하는 값.
    - 형식 `{ type: 'ACTION_TYPE', payload: 데이터 };`
  
  - **리듀서 함수**(reducer function)
    - 형식
      ```tsx
      function reducer(state:StateType, action:ActionType) {
        switch (action.type) {
            case 'ACTION_TYPE_1':
                return { ...state, 변경_값 }; // 새로운 상태 반환
            case 'ACTION_TYPE_2':
                return { ...state, 변경_값 }; // 새로운 상태 반환
            default:
                return state: // 변경이 없을 경우 이전 상태 유지
        }
      }
      ```

- 파일 확장자
  - .tsx: JSX를 포함하는 파일(컴포넌트)
  - .ts: 유틸 함수, 리듀서, 타입 선언, API 모듈 등 JSX가 없는 파일

---

## 4.4, 상태 관리 패턴
## 4.5, 개발자 도구로 상태 값 확인하기

---

# 8장, 폼 다루기

---

## 8.1, 폼 정의하기

- HTML에서 **폼**(form)은 사용자가 정보를 입력하고 제출할 수 있도록 구성된 다양한 UI 요소의 집합입니다.

## 8.2, 폼 제어하기

- 리액트에서는 폼 요소에 입력된 값을 어떻게 제어하느냐에 따라 제어 컴포넌트와 비제어 컴포넌트로 나눌 수 있음.

## 8.2.1, 제어 컴포넌트

* **제어 컴포넌트**(controlled component): 입력 값을 리액트 컴포넌트의 상태로 완전히 관리하는 방식.

- 제어 컴포넌트는 다음과 같은 순서로 작동
  1. 상태 정의
  2. 상태 업데이트
  3. 상태 입력 요소 연결

* e.target.value
* **계산된 속성 이름**(computed property name), 키 이름을 런타임 값으로 결정해야 할 때 쓰는 문법.

## 8.2.2, 비제어 컴포넌트

* **비제어 컴포넌트**(unControlled component): 폼 요소의 입력 값을 리액트 상태가 아닌 DOM 자체에서 직접 관리하는 방식.
  - 이 방식에서는 useState 훅 대신 useRef 훅을 사용해 DOM 요소에 직접 접근해 값을 읽거나 조작합니다.

- useRef 훅은 다음과 같이 사용.
  1. useRef 훅으로 참조 생성
    - 형식
      ```tsx
      import { useRef } from 'react';
      const ref = useRef<Type>(initialValue);
      ```
  2. 입력 요소에 ref 객체 연결

* 제어 컴포넌트가 입력 값을 항상 상태로 감시하는 방식이라면 비제어 컴포넌트는 필요할 때만 값을 가져오는 방식.

- 옵셔널 체이닝(optional chaining)