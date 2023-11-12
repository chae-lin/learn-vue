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

export default {
  data() {
    return {
      userName: "",
      password: "",
    };
  },
  methods: {
    submitForm() {
      // event.preventDefault(); -> @submit.prevent

      const data = { userName: this.userName, password: this.password };
      axios
        .post("https://jsonplaceholder.typicode.com/users/", data)
        .then((response) => {
          console.log(response);
        });
    },
  },
};
</script>

<style scoped></style>
