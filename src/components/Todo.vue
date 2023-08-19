<template>
  <div :class="['todo', { completed: todo.isDone }]">
    <div class="todo__info">
      <p class="break-all sm:break-auto">{{ todo.content }}</p>
    </div>
    <div class="todo__actions">
      <button v-if="todo.status === 'todo'" @click="emit('complete')">
        <img
          src="../assets/images/checkmark.png"
          alt="checkmark icon"
          class="w-5"
        />
      </button>
      <button @click="emit('delete')">
        <img src="../assets/images/x.png" alt="x icon" class="w-5" />
      </button>
      <button @click="emit('archive')">
        <img
          src="../assets/images/flashback.png"
          alt="flashback icon"
          class="w-5"
        />
      </button>
    </div>
  </div>
</template>

<script setup>
defineProps(["todo"]);

const emit = defineEmits(["delete, complete, archive"]);
</script>

<style scoped lang="postcss">
.todo {
  @apply grid grid-cols-1 sm:grid-cols-12 sm:gap-12 gap-2 text-center sm:text-left justify-between items-center bg-[#8083e4] rounded pl-2 sm:py-4 py-3;
}

.todo:hover {
  @apply bg-[#6b6fe6];
}

.todo .todo__info {
  @apply sm:col-span-9 gap-2 sm:text-2xl text-xl text-white;
}

.todo__actions button {
  @apply sm:text-4xl text-2xl text-white cursor-pointer sm:ml-3 ml-2 opacity-80 duration-200;
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

.img {
  @apply w-1;
}
</style>
