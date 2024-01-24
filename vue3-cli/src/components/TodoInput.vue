<template>
  <div class="todo-add">
    <input type="text" v-model="inpuValue" @keyup.enter="onPressEnter" />
    <button type="button" @click="onAddTodo">추가</button>
  </div>
</template>

<script setup>
import { ref, defineEmits } from "vue";

const inpuValue = ref("");

const emit = defineEmits(["addedValue"]);

const eventClearTodo = () => {
  inpuValue.value = "";
};

const eventAddTodo = () => {
  if (!inpuValue.value) {
    return false;
  }
  const todoValue = inpuValue.value;
  emit("addedValue", todoValue);
  eventClearTodo();
};

const onAddTodo = () => {
  eventAddTodo();
};

const onPressEnter = () => {
  eventAddTodo();
};
</script>
<!-- <script>
export default {
    // props: ["propsName"],
    setup(props, context) {
        const todoInput = ref("");
        const addTodo = () => {
            const todo = todoInput.value;
            localStorage.setItem(todo, todo);
            context.emit('add', todo);
        };
    }
}
</script> -->

<style lang="scss" scoped>
.todo-add {
  display: flex;
  align-items: center;
  justify-content: center;

  input {
    width: 80%;
    height: 38px;
    box-sizing: border-box;
  }
  button {
    width: 80px;
    height: 38px;
    margin-left: 6px;
    font-size: 16px;
    line-height: 1;
    color: #fff;
    background-color: #000;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
}
</style>
