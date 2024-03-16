<template>
  <div class="container">
    <h1 class="mt-4 mb-3">Jednoduchý Todo List - Vetiška</h1>
    <div class="input-group mb-3">
      <input type="text" class="form-control" placeholder="Přidat nový úkol" v-model="newTodo">
      <div class="input-group-append">
        <button class="btn btn-outline-primary" @click="addTodo">Přidat</button>
      </div>
    </div>
    <ul class="list-group">
      <li class="list-group-item" v-for="(todo, index) in todos" :key="index">
        {{ todo }}
        <button class="btn btn-sm btn-success float-right" @click="removeTodo(index)">Hotovo</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodo: '',
      todos: []
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim() !== '') {
        this.todos.push(this.newTodo);
        this.newTodo = '';
      }
    },
    removeTodo(index) {
      this.todos.splice(index, 1);
    }
  }
};
</script>

<style>

</style>
