<template>
  <div class="overall">
    <Header @changeState="changeTab" />
    <TaskList :currentTab="tab" />
  </div>
</template>

<script setup>
import Header from "./components/Header.vue";
import TaskList from "./components/TaskList.vue";
import { ref } from "vue";

const tab = ref("todo");

function changeTab(tabName) {
  tab.value = tabName;
}
</script>

<style scoped lang="postcss">
.overall {
  @apply flex w-screen h-screen bg-white justify-center items-center flex-col;
}
</style>
