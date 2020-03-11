<template>
  <div id="app">
    <Header />
    <TodoAdd v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Header from './components/layout/Header'
import Todos from './components/Todos'
import TodoAdd from './components/TodoAdd'

export default {
  name: 'App',
  components: {
    Header,
    TodoAdd,
    Todos
  },
  data(){
    return{
      todos: [
        {
          id:1,
          title:'Todo one',
          completed:false
        },
        {
          id:2,
          title:'Todo Two',
          completed:false
        },
        {
          id:3,
          title:'Todo three',
          completed:false
        },
      ]
    }
  },
  methods:{
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addTodo(newTodo){
      this.todos = [...this.todos, newTodo]
    }
  }
}
</script>

<style>

</style>
