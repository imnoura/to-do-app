<template>
  <div class="todo-box">
    <form v-if="currentTab === 'todo'" @submit.prevent="newTask">
      <input type="text" placeholder="New task..." v-model="todoInput" />
      <button :disabled="!todoInput">Add</button>
    </form>
    <div class="todo-list">
      <Todo
        v-for="(todo, index) in todos"
        :todo="todo"
        :key="todo.id"
        @delete="deleteTodo(index)"
        @complete="completeTodo(index)"
      />
    </div>
  </div>
</template>

<script setup>
import { reactive, ref } from "vue";
import Todo from "./Todo.vue";

defineProps({
  currentTab: String,
});

const todos = reactive([]);

const todoInput = ref("");

function newTask() {
  todos.unshift({
    id: Math.random,
    content: todoInput.value,
    isDone: false,
  });
  todoInput.value = "";
}

function completeTodo(index) {
  todos[index].isDone = !todos[index].isDone;
}

function deleteTodo(index) {
  todos.splice(index, 1);
}
</script>

<style scoped lang="postcss">
form {
  @apply sm:w-[595px] justify-evenly flex sm:flex-row flex-col mx-4;
}

form input {
  @apply sm:w-[400px] text-[#4101cc] text-2xl px-3 sm:py-4 py-3 bg-[#ccceff] border-solid border-2 border-[#bbbdf6] rounded-lg;
}

form button {
  @apply sm:mt-0 mt-3 text-2xl px-16 sm:py-4 py-3 rounded-lg bg-[#8083e4] text-white;
}

form button:hover {
  @apply bg-[#6b6fe6];
}

form button[disabled] {
  @apply sm:mt-0 mt-3 text-2xl px-16 sm:py-4 py-3 rounded-lg bg-[#8083e4] text-white cursor-not-allowed;
}

.todo-box {
  @apply bg-[#dedfff] rounded-lg py-7 mx-7 shadow-lg w-[302px] sm:w-[630px];
}

.todo-list {
  @apply flex flex-col gap-4 mt-5 mx-4 sm:mx-5;
}

.todo {
  @apply grid grid-cols-1 sm:grid-cols-12 sm:gap-12 gap-2 text-center sm:text-left justify-between items-center bg-[#8083e4] rounded sm:py-4 py-3;
}

.todo:hover {
  @apply bg-[#6b6fe6];
}

.todo .todo__info {
  @apply sm:col-span-9 gap-2 sm:text-2xl text-xl text-white;
}

.todo__actions button {
  @apply sm:text-4xl text-2xl text-white cursor-pointer sm:ml-3 opacity-80 duration-200;
}
.todo__actions {
  @apply col-span-3;
}
.todo__actions button:hover {
  @apply opacity-100;
}

.todo input {
  @apply w-7 h-7;
}
</style>
