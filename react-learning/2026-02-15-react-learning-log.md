# React learning, Day 31 (실제: Day 19)
Date : 2026-02-15 Sunday.

---

# 12장, 전역 상태 관리.

## 12.1.1, 로컬 상태 관리

* **로컬 상태 관리**: useState나 useReducer와 같은 훅을 사용해 각 컴포넌트 내부에서 상태를 관리하는 방식.

- **로컬(local) 상태**
- **상태 끌어올리기**(state lifting) 패턴

---

## 12.1.2, 전역 상태 관리

* **전역 상태 관리**: 상태를 애플리케이션 전체에서 공유 가능한 형태로 관리하는 방식.
* **프레젠테이셔널 컴포넌트**(presentational component): UI만 담당하고 상태 변경은 하지 않는 컴포넌트.
* **컨테이너 컴포넌트**(container component): 데이터를 단순히 중간에서 넘겨주는 역할을 하는 컴포넌트.

- 리액트에서는 다음과 같은 전역 상태 관리 방법을 제공함.
  - Context API(리액트 기본 제공)
  - Redux Toolkit
  - Zustand

---

