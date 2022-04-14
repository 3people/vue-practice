- html에서 vue를 사용하려면 cdn를 추가하면 된다.

  ```html
  <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  ```

- `v-if`와 `v-else`를 사용하려면 형제 태그이면서 인접해야 한다.

  ```html
  <div v-if="liked">좋아요 눌렀음</div>
  <button v-else v-on:click="onClickButton">Like</button>
  ```

- `v-model`을 사용하여 양방향 데이터 바인딩이 가능하다.

  - 양방향 데이터 바인딩이란?
    데이터 변경에 따라 프레임워크를 통해 양방향으로 이루어지며 뷰가 즉각 업데이트 된다.
  - 단방향 데이터 바인딩이란?
    적절한 Event를 통해 데이터 흐름이 단방향으로 이루어지고 뷰가 바로 업데이트 되지 않는다.

- `e.preventDefault()`를 통해 form 제출 시 새로고침 방지
