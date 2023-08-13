<template>
  <div class="overall">
    <Header />
    <TaskList />
  </div>
</template>

<script setup>
import Header from "./components/Header.vue";
import TaskList from "./components/TaskList.vue";
</script>

<style scoped lang="postcss">
.overall {
  @apply flex w-screen h-screen bg-white justify-center items-center flex-col;
}
</style>
