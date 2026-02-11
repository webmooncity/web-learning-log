# React learning, Day 27 (실제: Day 17)
Date : 2026-02-11 Wednesday.

---

## 11.4, 값 메모이제이션.

## 11.4.1, 연산 비용이 큰 작업의 성능 저하 문제

## 11.4.2, useMemo 훅 사용하기

* **useMemo**: 리액트에서 제공하는 훅 중 하나로, 값을 메모이제이션할 때 사용.
  - useCallback 훅은 함수 자체를 메모이제이션하는 반면, useMemo는 함수의 반환 값을 메모이제이션하는 점에서 차이가 있음.
  - 형식: `const cachedValue = useMemo(claculateValue, dependencies);`

## 11.4.3, useMemo 훅 사용 시 주의사항

* useCallback 훅은 함수를, useMemo 훅은 값을 메모이제이션하는 것이 목적.

---

## 11.5, 로딩 성능 최적화

- 코드 스플리팅, React.Suspense, ErrorBoundary

## 11.5.1, React.lazy()를 사용한 코드 스플리팅

* **코드 스플리팅**(code splitting): 애플리케이션의 코드를 청크 단위로 분할하고, 필요한 시점에만 해당 청크를 로드해 초기 렌더링 시 불필요한 코드의 로드를 지연시키는 최적화 기법.

* React.lazy()

## 11.5.2, Suspense

* **Suspense**: 비동기 작업이 완료될 때까지 렌더링을 일시 중지하는 기능을 제공함. 주로 코드 스플리팅이나 데이터 패칭처럼 지연 로딩할 때 활용함.
- **데이터 패칭**(data fetching): 애플리케이션이 외부 API나 데이터베이스에서 필요한 데이터를 요청하고 받아오는 작업을 의미함.

## 11.5.3, ErrorBoundary

* **ErrorBoundary**: 오류 복구용 컴포넌트 패턴으로, 컴포넌트 트리 내부에서 자바스크립트 오류가 발생해도 애플리케이션 전체가 멈추지 않도록 보호해 줌.


* JavaScript와 TypeScript 기초가 부족하다. React 진도가 끝나면, 더 공부해야 겠다.