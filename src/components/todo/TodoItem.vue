<script setup lang="ts">
import { ref } from 'vue'

interface TodoItem {
  id: number
  text: string
  completed: boolean
}

const todos = ref<TodoItem[]>([])
const newTodo = ref('')

function addTodo() {
  if (newTodo.value.trim()) {
    todos.value.push({
      id: Date.now(),
      text: newTodo.value,
      completed: false,
    })
  }
}
</script>

<template>
  <button @click="addTodo" class="submit-button">Add</button>
  <input type="text" v-model="newTodo" placeholder="Enter Todo Here" class="todo-input" />
</template>

<style>
.submit-button {
  background-color: gray;
  border-radius: 4px;
  color: white;
  padding: 0.5rem;
  margin-top: 0.5rem;
  margin-right: 0.5rem;
}
.todo-input {
  border: 1px solid gray;
  padding: 0.5rem;
}
</style>
