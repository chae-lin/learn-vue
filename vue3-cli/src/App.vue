<template>
  <TodoHeader :title="TodoHeaderTitle"></TodoHeader>
  <!-- <TodoInput @하위컴포넌트 이벤트 이름="상위컴포넌트 메서드 이름"></TodoInput> -->
  <TodoInput @addedValue="addTodoItem"></TodoInput>
  <!-- <TodoList :프롭스 이름="상위컴포넌트 데이터 이름"></TodoList> -->
  <TodoList :todoItmes="todoItmes" @removeValue="removeTodoItem"></TodoList>
</template>

<script setup>
import { onBeforeMount, ref } from "vue";
import TodoHeader from "./components/TodoHeader.vue";
import TodoInput from "./components/TodoInput.vue";
import TodoList from "./components/TodoList.vue";

const todoItmes = ref([]);
const TodoHeaderTitle = ref("할일 앱");

const fetchTodos = () => {
  const result = [];
  for (let index = 0; index < localStorage.length; index++) {
    const todoItem = localStorage.key(index);
    result.push(todoItem);
  }

  return result;
};

// 라이플 사이클 API
onBeforeMount(() => {
  todoItmes.value = fetchTodos();
});

const addTodoItem = (todoValue) => {
  todoItmes.value.push(todoValue);
  localStorage.setItem(todoValue, todoValue);
};

const removeTodoItem = (item, index) => {
  todoItmes.value.splice(index, 1);
  localStorage.removeItem(item);
};
</script>

<style lang="scss" scoped></style>
