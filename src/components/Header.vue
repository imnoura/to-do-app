<template>
  <div>
    <button>To Do</button>
    <button>Done</button>
  </div>
</template>

<script setup>
defineProps({});
</script>

<style scoped lang="postcss">
button {
  @apply bg-[#A880E4] rounded-sm border-2 border-solid border-[#A880E4] mb-5 py-7 px-36;
}
</style>
