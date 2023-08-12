<template>
  <div class="overall">
    <Header />
    <TaskColumn />
  </div>
</template>

<script setup>
import Header from "./components/Header.vue";
import TaskColumn from "./components/TaskColumn.vue";
</script>

<style scoped>
.overall {
  @apply flex w-screen h-screen bg-white justify-center items-center flex-col;
}
</style>
