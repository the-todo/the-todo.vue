<script setup>
import { reactive } from 'vue';

const todos = reactive({
  list: [],
  // 'ALL' | 'FINISHED' | 'UNFINISHED'
  filter: 'ALL',
  nextId: 0,
});

const addTodo = (text) => {
  const { list, id } = todos;
  list.push({ text, id: id + 1, isFinished: false });
};

const setFilter = (filter) => {
  todos.filter = filter;
};
</script>

<template>
  <div class="d-flex justify-content-between align-items-center mt-3">
    <button
      class="btn btn-outline-primary"
      @click="decrement"
    >-</button>
    {{ count }}
    <button
      class="btn btn-outline-primary"
      @click="increment"
    >+</button>
  </div>
</template>
