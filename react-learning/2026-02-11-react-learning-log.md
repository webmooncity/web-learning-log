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