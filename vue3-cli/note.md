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
