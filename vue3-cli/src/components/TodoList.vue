<template>
  <ul class="todo-list">
    <li v-for="(item, index) in props.todoItmes" :key="index">
      <span>{{ item }}</span>
      <button type="button" @click="removeTodo(item, index)">삭제</button>
    </li>
  </ul>
</template>

<script setup>
import { defineProps, defineEmits } from "vue";

const props = defineProps({
  todoItmes: Array,
});

const emit = defineEmits(["removeValue"]);

const removeTodo = (item, index) => {
  emit("removeValue", item, index);
};
</script>

<style lang="scss" scoped>
/* <style> 태그가 scoped 속성을 가지고있을 때, CSS는 현재 컴포넌트의 엘리먼트에만 적용됩니다. */
.todo-list {
  list-style: none;
  margin: 16px 0 0;
  padding: 0;
  border-top: 1px solid #000;
  li {
    display: flex;
    align-items: center;
    padding: 10px 4px;
    border-bottom: 1px solid #000;
    span {
      flex: 1;
    }
    button {
      margin-left: 4px;
      flex-shrink: 0;
      font-size: 12px;
      color: #828282;
      background-color: transparent;
      border: 1px solid #d9d9d9;
      border-radius: 2px;
      cursor: pointer;
    }
  }
}
</style>
