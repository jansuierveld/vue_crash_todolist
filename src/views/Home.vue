<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
  
  import AddTodo from '../components/AddTodo';
  import Todos from '../components/Todos';
  import axios from 'axios';

  export default {
    name: 'Home',
    components: {
      Todos, AddTodo
    },
    data(){
      return {
        todos: []
      }
    },
    methods: {
      deleteTodo(id){
        // deleten naar jsonplaceholder (niet echt)
        axios.delete('https://jsonplaceholder.typicode.com/todos/${id}')
        .then(res =>this.todos = this.todos.filter(todo => todo.id !== id))
        .catch(err => console.log(err));
        //this.todos = this.todos.filter(todo => todo.id !== id);
      },
      addTodo(newTodo){
        const {title, completed} = newTodo;
        // posten naar jsonplaceholder (niet echt)
        axios.post('https://jsonplaceholder.typicode.com/todos', {
          title, completed
        })
        .then(res =>this.todos = [...this.todos, newTodo])
        .catch(err => console.log(err));
      }
    },
    created() {
        // created laadt bij opstarten component. LET OP BUITEN methods

        // axios is een http library en de get retourneeert een promise
        // axios.get('https://jsonplaceholder.typicode.com/todos')
        axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
        .then(res => this.todos= res.data)
        .catch(err => console.log(err));
      }

  }
</script>

<style>
  * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
  }
  body {
    font-family: Atial, Helvetica, sans-serif;
    line-height: 1.4;
  }

  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor:pointer;
  }
  .btn:hover {
    background: #666;
  }
</style>

