<template>
  <div class="container">
    <div class="todo-box">
      <h1>My Todo-s</h1>

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
import { reactive, ref } from "vue";
</script>

<style scoped>
.container {
  display: flex;
  width: 100vw;
  height: 100vh;
  background-color: white;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  gap: 8px;
}

h1 {
  color: rgb(69, 69, 69);
  font-weight: 900;
  margin-bottom: 48px;
  text-align: center;
}

form {
  margin-bottom: 24px;
}

form input {
  width: 500px;
  font-size: 24px;
  padding: 8px;
  color: rgb(75, 75, 75);
  outline: none;
  border: solid 2px rgb(162, 162, 162);
  border-radius: 8px;
}

form button {
  margin-left: 8px;
  font-size: 24px;
  padding: 8px;
  border-radius: 8px;
  border: solid 2px #49994c;
  background-color: #4caf50;
  color: white;
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
  background-color: #eeeeee;
  border-radius: 8px;
  border: solid 2px rgb(201, 201, 201);
  box-shadow: 0px 0px 20px rgb(179, 179, 179);
  padding: 36px;
}

.todo-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.todo {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: rgb(230, 230, 230);
  border-radius: 4px;
  padding: 0 8px;
}

.todo:hover {
  background-color: rgb(216, 216, 216);
}

.todo.completed {
  opacity: 0.4;
}

.todo.completed p {
  text-decoration: line-through;
}

.todo .todo__info {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 24px;
}

.todo__actions button {
  border: none;
  font-size: 18px;
  cursor: pointer;
  filter: grayscale(1);
  opacity: 0.7;
  transition: 0.2s;
  background-color: transparent;
}

.todo__actions button:hover {
  filter: grayscale(0);
  opacity: 1;
}

.todo input {
  width: 24px;
  height: 24px;
}
</style>
