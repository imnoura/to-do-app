<template>
  <div
    class="@apply flex w-[302px] sm:w-[630px] h-16 bg-[#8083e4] mb-5 rounded-lg"
  >
    <button @click="$emit('changeState', 'To Do')">To Do</button>
    <button @click="$emit('changeState', 'Done')">Done</button>
  </div>
</template>

<script setup></script>

<style scoped lang="postcss">
button {
  @apply flex-1 justify-evenly bg-[#8083e4] rounded-lg text-2xl text-white;
}

button:hover {
  @apply bg-[#6b6fe6];
}
</style>
