<template>
  <AppHeader v-bind:appTitle="massage" v-on:change="changeMassage"></AppHeader>
  <!-- v-on: 은 @ 로 축약가능 -->
  <button type="button" @click="showAlert">경고</button>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";

export default {
  components: {
    // '컴포넌트 이름': 컴포넌트 내용
    // AppHeader: AppHeader, (키와 벨류가 똑같을 때 하나의 단어로 축약 가능)
    AppHeader,
  },
  data() {
    return {
      massage: "앱해더 프롭스 초기 값",
    };
  },
  methods: {
    showAlert() {
      alert("hello");
    },
    changeMassage() {
      this.massage = "앱해더 프롭스를 변경됨";
    },
  },
};
</script>

<style scoped></style>
