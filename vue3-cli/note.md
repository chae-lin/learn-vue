### 기본 코드 작성

- vue 다운로드

```Bash
npm i @vue/cli -g
```

- 프로젝트 생성

```Bash
vue create 컴포넌트 네임
```

### Vue Composition API 장점

- 타입 추론에 용이
- 로직 재사용성 (별도의 파일로 분리 후 import 하여 사용가능.)

### Vue Composition API 단점

- 불필요한 전환 비용 (컴포넌트가 세분화하여 역활별로 분리 필요/ 반복되는 코드가 있는 경우 모듈화)
- 데이터와 매서드의 명확한 구분 필요.

### 인스턴스 라이프사이클

뷰의 인스턴스가 생성되어 소멸되기까지 거치는 과정을 의미.
인스턴스가 생성되고 나면 라이브러리 내부적으로 다음과 같은 과정이 진행됨.

├── 인스턴스 생성
│ ├── beforeCreate
│ ├── created
│ ├── beforeMount
│ └── mounted
├── 인스턴스를 화면에 부착
│ ├── beforeUpdate
│ └── updated
├── 인스턴스 내용 갱신
│ ├── beforeDestroy
│ └── destroyed
└── 인스턴스 소멸

### 라이프사이클 훅

- created(opens new window)
- beforeMount(opens new window)
- mounted(opens new window)
- destroyed
- ...

### Lifecycle API

컴포지션(Composition API)에서 사용된 인스턴스 라이프사이클 훅을 의미.

- beforeCreate, created 대신에 setup() 을 사용
- onXX 형태로 이름이 변형
- beforeDestory, destroyed 등 destory 대신에 onBeforeUnmount, onUnmounted를 사용

| 인스턴스 라이프사이클 훅 | 라이프사이클 API | 비고                                 |
| ------------------------ | ---------------- | ------------------------------------ |
| beforeCreate             | X                | 대신 setup()                         |
| created                  | X                | 대신 setup() 사용                    |
| beforeMount              | onBeforeMount    |                                      |
| mounted                  | onMounted        |                                      |
| beforeUpdate             | onBeforeUpdate   |                                      |
| updated                  | onUpdated        |                                      |
| beforeDestroy            | onBeforeUnmount  | destory 라는 표현이 unmount로 변경됨 |
| destroyed                | onUnmounted      | destory 라는 표현이 unmount로 변경됨 |
| errorCaptured            | onErrorCaptured  |                                      |
