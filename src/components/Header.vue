<template>
  <div class="@apply bg-[#8083e4] mb-5 rounded-lg">
    <button>To Do</button>
    <button>Done</button>
  </div>
</template>

<script setup>
defineProps({});
</script>

<style scoped lang="postcss">
button {
  @apply bg-[#8083e4] rounded-lg py-7 px-32 text-2xl text-white;
}
button:hover {
  @apply bg-[#6b6fe6];
}
</style>
