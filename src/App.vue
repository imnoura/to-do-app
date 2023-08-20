<template>
  <div class="overall">
    <Header @changeState="changeTab" />
    <TaskBox :currentTab="tab" />
  </div>
</template>

<script setup>
import Header from "./components/Header.vue";
import TaskBox from "./components/TaskBox.vue";
import { ref } from "vue";

const tab = ref("todo");

function changeTab(tabName) {
  tab.value = tabName;
}
</script>

<style scoped lang="postcss">
.overall {
  @apply flex w-screen h-screen bg-[#313575] justify-center items-center flex-col;
}
</style>
