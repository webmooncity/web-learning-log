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

## 12.2, Context API로 전역 상태 관리하기

- **Context API**: 컴포넌트 트리 내에서 상태나 값을 전역적으로 공유할 수 있게 하는 기능을 제공함.
- **컨텍스트**(context): 프로그래밍에서 컴포넌트들이 공통으로 사용하는 데이터의 흐름이나 의미를 담는 공간을 의미함.
- **API**(Application Programming Interface): 다양한 소프트웨어 컴포넌트가 상호작용할 수 있게 하는 인터페이스를 의미함.

- Context API를 사용하려면 다음 두 가지 작업을 해야 함.
  1. 컨텍스트 객체 생성 및 제공.
  2. 컨텍스트 값 소비.

### 12.2.1, 컨텍스트 객체 생성.

- **컨텍스트 객체**: 데이터를 전역으로 공유하기 위한 매개체 역할을 함.
- **Provider**: 컨텍스트의 데이터를 하위 컴포넌트에 공급하는 컴포넌트.

- createContext() 함수
  - 형식: `const SomeContext = createContext<DataType>(defaultValue);`

### 12.2.2, Provider로 컨텍스트 범위 지정하기.

- Provider 컴포넌트
  - 형식: 
  ```tsx
  <컨텍스트_객체 value={공유할_데이터}>
    공유할_컴포넌트
  </컨텍스트_객체>
  ```

### 12.2.3, useContext 커스텀 훅 만들기

- useContext: Context API로 공유된 값을 하위 컴포넌트에서 직접 가져올 수 있게 해주는 훅
  - 형식: `const value = useContext(SomeContext);`

---