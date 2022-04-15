- vue component에서는 data를 사용할 때 함수로써 사용해야 된다.

  ```js
  /// X
  Vue.component("my-component", {
    data: {
      message: "hello",
    },
  });

  /// O
  Vue.component("my-component", {
    data: function () {
      return {
        message: "hello",
      };
    },
  });
  ```

- vue의 html에서는 kebab-case 사용하기!
