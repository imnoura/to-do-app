<template>
  <div class="flex w-[302px] sm:w-[630px] h-16 bg-[#8083e4] mb-5 rounded-lg">
    <button
      @click="onTabChange('all')"
      :class="{ active: activeTab === 'all' }"
    >
      All
    </button>
    <button
      @click="onTabChange('todo')"
      :class="{ active: activeTab === 'todo' }"
    >
      To Do
    </button>
    <button
      @click="onTabChange('done')"
      :class="{ active: activeTab === 'done' }"
    >
      Done
    </button>
    <button
      @click="onTabChange('archive')"
      :class="{ active: activeTab === 'archive' }"
    >
      Archive
    </button>
  </div>
</template>

<script setup>
import { ref } from "vue";
const emit = defineEmits(["changeState"]);

const activeTab = ref("todo");

function onTabChange(tabName) {
  activeTab.value = tabName;
  emit("changeState", tabName);
}
</script>

<style scoped lang="postcss">
button {
  @apply flex-1 justify-evenly bg-[#8083e4] rounded-lg sm:text-2xl text-lg  text-white;
}

button:hover {
  @apply bg-[#6b6fe6];
}

div:hover {
  @apply bg-[#6b6fe6];
}

.active {
  @apply bg-[#6b6fe6];
}
</style>
