<template>
  <div id="app">
    <h1>Список дел на день</h1>
    <hr>
    <ListDel
    v-bind:todos="todos"
    @remove-todo="removeTodo"
    />
  </div>
</template>

<script>

import ListDel from '@/components/ListDel'
export default {
  name: 'App',
  data(){
    return{
      todos: [
          {id:1, title : 'Проснуться', completed: false},
          {id:2, title : 'Позавтракать', completed: false},
          {id:3, title : 'Написать тестовое задание', completed: false}
      ]

    }
  },
  methods: {
    removeTodo(id){
      this.todos = this .todos.filter(t =>t.id!==id)
    }
  },
  components: {
    ListDel
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
