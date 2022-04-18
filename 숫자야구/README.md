- package.json의 용도

  - 프로젝트 정보 정의
  - 의존하는 패키지 버전 정보 명시

- package.json에서 tilde(~)와 carrot(^)의 차이
  |구분|설명|예시|
  |:--:|:--:|:--:|
  |틸드(~)|x.y.z 중 z 범위 내에서 버전 업데이트|~1.1.0: 1.1.0 <=, 1.2 >|
  |캐럿(^)|x.y.z 중 x 이하 하위호환성이 보장되는 범위 내에서 버전 업데이트|^1.1.0: 1.1.0 <=, 2.0 >|

- webpack을 사용하는 이유?
  html에 들어가는 여러 js 파일들을 하나의 js 파일로 관리하기 위해

- webpack build시 absolute path가 필요할 때 node에서 제공하는 path module을 사용하자!

  ```javascript
    const path = require("path");
    ...
    path: path.join(__dirname, 'dist')
  ```

- webpack 오류 해결하기

  - webpack은 js를 번들링하는데 `.vue` 파일을 만나면 js 문법이 아니기 때문에 오류를 뱉는다. 따라서 `.vue` 파일을 만났을 땐 `vue-loader`가 처리하게 webpack 설정을 해준다.

  ```javascript
  module: {
    rules: [
      {
        test: /\.vue$/,
        loader: "vue-loader",
      },
    ],
  },
  ```

  - vue, vue-loader, vue-template-complier, webpack, webpack-cli의 버전을 적절하게 맞춰야 한다.

  ```json
  "dependencies": {
    "vue": "^2.6.14"
  },
  "devDependencies": {
    "@vue/compiler-sfc": "^3.2.33",
    "vue-loader": "^15.9.6",
    "vue-template-compiler": "^2.6.14",
    "webpack": "^5.1.3",
    "webpack-cli": "^4.3.1"
  }
  ```

- `v-on:`은 `@`로 대체 가능, `preventDefault()`는 `.prevent`로 대체 가능
  ```html
  <form v-on:submit></form>
  <form @submit.prevent></form>
  ```
