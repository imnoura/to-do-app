<template>
  <div class="overall">
    <Header />
    <div class="todo-box">
      <form>
        <input type="text" placeholder="Add new..." />
        <button>Add</button>
      </form>

      <hr />

      <div class="todo-list">
        <div class="todo completed">
          <div class="todo__info">
            <input type="checkbox" checked />
            <p>Buy a new laptop!</p>
          </div>
          <div class="todo__actions">
            <button>❌</button>
          </div>
        </div>
        <div class="todo">
          <div class="todo__info">
            <input type="checkbox" />
            <p>Buy some milk</p>
          </div>
          <div class="todo__actions">
            <button>❌</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import Header from "./components/Header.vue";
</script>

<style scoped>
.overall {
  @apply flex w-screen h-screen bg-white justify-center items-center flex-col;
}

h1 {
  color: rgb(69, 69, 69);
  font-weight: 900;
  margin-bottom: 48px;
  text-align: center;
}

form {
  @apply w-[595px] justify-evenly flex mb-6 mx-4;
}

form input {
  @apply w-[400px] text-2xl px-3 py-4 bg-[#ccceff] border-solid border-2 border-[#bbbdf6] rounded-lg;
}

form button {
  @apply ml-2 text-2xl py-4 px-16 rounded-lg border-solid border-2 bg-[#8083e4] text-white;
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
hr {
  margin-bottom: 18px;
  display: block;
  opacity: 0.3;
}

.todo-box {
  @apply bg-[#dedfff] rounded-lg py-7 mx-7 shadow-lg;
}

.todo-list {
  @apply flex flex-col gap-4 mx-5;
}

.todo {
  @apply flex justify-between items-center bg-[#8083e4] rounded py-4 px-3 w-auto;
}

.todo:hover {
  @apply bg-[#6b6fe6];
}

.todo.completed {
  @apply opacity-40;
}

.todo.completed p {
  @apply line-through;
}

.todo .todo__info {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 24px;
}

.todo__actions button {
  @apply text-2xl border-none cursor-pointer opacity-70 duration-200 bg-transparent;
}

.todo__actions button:hover {
  opacity: 1;
}

.todo input {
  @apply w-7 h-7;
}
</style>
