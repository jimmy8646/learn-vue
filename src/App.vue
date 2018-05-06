<template>
  <div>
    <div id="app">
      <img src="./assets/logo.png">
      <h1>{{ msg }}</h1>
    </div>
    <div class="container">
      <form v-on:submit.prevent="addTodo(newTodo)">

        <div class="form-group">
          <input type="text" class="form-control form-control-lg" v-model="newTodo.title" placeholder="寫點東西吧">
        </div>
        <div class="form-group">
          <button class="btn btn-success" type="submit">加加</button>
        </div>
      </form>

      <ul class="list-group">
        <li v-for="(todo,index) in todos" class="list-group-item">
          {{todo.title}}
          <button class="btn btn-warning btn-xs pull-right" v-on:click="removeTodo(index)">X</button>
        </li>
      </ul>
    </div>
  </div>


</template>

<script>
  export default {
    name: 'app',
    data() {
      return {
        msg: 'Vue js 真牛',
        todos: [
          {id:1,title:'Learn Vuejs'}
        ],
        newTodo: {
          id: null,
          title: ''
        }
      }
    },
    methods: {

      addTodo(newTodo) {
        this.todos.push(newTodo)
        this.newTodo = {id: null,title: ''}
      },

      removeTodo(index) {
        this.todos.splice(index, 1)
      }
    },
  }

</script>

<style lang="scss">
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  h1,
  h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }

</style>
<style lang="scss">
  @import '../node_modules/bootstrap/scss/bootstrap.scss';

</style>
