<!-- Vue Composition API 로 파일 변환하기 -->
<template>
  <!-- event.preventDefault 와 동일한 기능: .prevent -->
  <form action="" @submit.prevent="submitForm">
    <div>
      <label for="userID">ID:</label>
      <input id="userID" type="text" v-model="userName" />
    </div>
    <div>
      <label for="password">PW:</label>
      <input id="password" type="text" v-model="password" />
    </div>
    <button type="submit">로그인</button>
  </form>
</template>

<script>
import axios from "axios";
import { ref } from "vue";

export default {
  setup() {
    // data
    var username = ref("");
    var password = ref("");

    // methods
    var submitForm = () => {
      axios
        .post("https://jsonplaceholder.typicode.com/users/", {
          username: username.value,
          password: password.value,
        })
        .then((response) => {
          console.log(response);
        });
    };

    return { username, password, submitForm };
  },
};
</script>

<style lang="scss" scoped></style>
