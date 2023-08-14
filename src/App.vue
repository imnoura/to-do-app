<template>
  <div class="overall">
    <Header @changeState="changeState" />

    <TaskList />
  </div>
</template>

<script setup>
import Header from "./components/Header.vue";
import TaskList from "./components/TaskList.vue";
import { ref } from "vue";

const taskState = ref("");

function changeState(state) {
  console.log(state);
  taskState.value = state;
  console.log(taskState);
}
</script>

<style scoped lang="postcss">
.overall {
  @apply flex w-screen h-screen bg-white justify-center items-center flex-col;
}
</style>
