<template>
  <!-- v-on: 은 @ 로 축약가능 -->
  <SectionTest v-bind:appTitle="massage" @change="changeMassage"></SectionTest>
  <button type="button" @click="showAlert">경고</button>
</template>

<script setup>
// ## composition 으로 변경하기

// 방법1.
// setup() {
//   const massage = ref("앱해더 프롭스 초기 값");
//   return( massage )
// }

import SectionTest from "@/components/SectionTest.vue";
import { ref } from "vue";

const massage = ref("앱해더 프롭스 초기 값");

const changeMassage = () => {
  massage.value = "앱해더 프롭스를 변경됨";
};

const showAlert = () => {
  alert("hello");
};
</script>

<!-- options <script>
import SectionTest from "@/components/SectionTest.vue";

export default {
  components: {
    // '컴포넌트 이름': 컴포넌트 내용
    // SectionTest: SectionTest, (키와 벨류가 똑같을 때 하나의 단어로 축약 가능)
    SectionTest,
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
</script> -->
