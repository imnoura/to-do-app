<template>
  <div :class="['todo', { completed: todo.isDone }]">
    <div class="todo__info">
      <p v-if="!editMode" class="flex items-center break-all sm:break-auto">
        <span>{{ todo.content }}</span>
        <span class="text-xs ml-2"> ({{ todo.status }}) </span>
      </p>
      <div v-else>
        <input type="text" placeholder="New task..." v-model="editText" />
      </div>
    </div>
    <div class="todo__actions">
      <button v-if="todo.status === 'todo'" @click="onEdit">
        <img src="../assets/images/edit.png" alt="edit icon" class="w-4" />
      </button>
      <button v-if="todo.status === 'todo'" @click="emit('complete')">
        <img
          src="../assets/images/checkmark.png"
          alt="checkmark icon"
          class="w-4"
        />
      </button>
      <button @click="emit('delete')">
        <img src="../assets/images/x.png" alt="x icon" class="w-4" />
      </button>
      <button @click="emit('archive')">
        <img
          src="../assets/images/flashback.png"
          alt="flashback icon"
          class="w-4"
        />
      </button>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const props = defineProps(["todo"]);

const emit = defineEmits(["delete, complete, archive, edit"]);
const editMode = ref(false);
const editText = ref("");

function onEdit() {
  if (!editMode.value) {
    editText.value = props.todo.content;
    editMode.value = true;
  } else {
    emit("edit", editText.value);
    editMode.value = false;
  }
}
</script>

<style scoped lang="postcss">
.todo {
  @apply grid grid-cols-1 sm:grid-cols-12 sm:gap-12 gap-2 text-center sm:text-left justify-between items-center bg-[#8083e4] rounded pl-2 sm:py-4 py-3;
}

.todo:hover {
  @apply bg-[#6b6fe6];
}

.todo .todo__info {
  @apply sm:col-span-8 gap-2 sm:text-2xl text-xl text-white;
}

.todo__actions button {
  @apply sm:text-4xl text-2xl text-white cursor-pointer sm:ml-3 ml-4 opacity-50 duration-200;
}
.todo__actions {
  @apply col-span-4 mr-6 sm:ml-6;
}
.todo__actions button:hover {
  @apply opacity-100;
}

.todo input {
  @apply w-7 h-7;
}

input {
  width: 250px !important;
  @apply text-[#4101cc] text-lg sm:py-4 py-3 bg-[#bdbfff] border-solid border-2 border-[#bbbdf6] rounded-lg;
}
</style>
