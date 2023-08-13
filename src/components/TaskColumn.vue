<template>
  <div class="todo-box">
    <form>
      <input type="text" placeholder="Add new..." />
      <button>Add</button>
    </form>
    <div class="todo-list">
      <div class="todo">
        <div class="todo__info">
          <p class="break-all sm:break-auto">
            Buy a new
            laptop!xcvhjkjhgfchgfdfghsdfsdfghsdfgnhfthsdfgfdghsdgfsdfgsdf
          </p>
        </div>
        <div class="todo__actions">
          <button>☑</button>
          <button>☒</button>
        </div>
      </div>
      <div class="todo">
        <div class="todo__info">
          <p>Buy some milk</p>
        </div>
        <div class="todo__actions">
          <button>☑</button>
          <button>☒</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup></script>

<style scoped>
form {
  @apply sm:w-[595px] justify-evenly flex sm:flex-row flex-col mb-6 mx-4;
}

form input {
  @apply sm:w-[400px] text-[#4101cc] text-2xl px-3 sm:py-4 py-3 bg-[#ccceff] border-solid border-2 border-[#bbbdf6] rounded-lg;
}

form button {
  @apply sm:mt-0 mt-3 text-2xl px-16 sm:py-4 py-3 rounded-lg bg-[#8083e4] text-white;
}

form button:hover {
  @apply bg-[#6b6fe6];
}

form button[disabled] {
  background-color: gray;
  border-color: gray;
  cursor: not-allowed;
  color: rgb(230, 230, 230);
}

.todo-box {
  @apply bg-[#dedfff] rounded-lg py-7 mx-7 shadow-lg w-[302px] sm:w-[630px];
}

.todo-list {
  @apply flex flex-col gap-4 mt-8 mx-4 sm:mx-5;
}

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
  @apply sm:text-4xl text-2xl text-white cursor-pointer sm:ml-3 ml-2  opacity-80 duration-200;
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
</style>
