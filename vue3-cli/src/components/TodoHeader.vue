<template>
  <h1>{{ newTtitle }}</h1>
</template>

<script setup>
import { computed, defineProps } from "vue";

const props = defineProps({ title: String });
const newTtitle = computed(() => {
  return props.title + "!!";
});
</script>
<style lang="scss" scoped></style>
