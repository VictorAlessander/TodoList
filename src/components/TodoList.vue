<template>
  <div class="todolist">
    <input type="text" v-model="newTodo">
    <button @click=addTodo()>+</button>
    <ul v-for="todo in todos">
      <li>{{ todo.title }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'TodoList',

  data () {
    return {
      newTodo: '',

      todos: []
    }
  },

  methods: {
    addTodo: function () {
      var task = this.newTodo.trim()

      if (task) {
        this.todos.push({
          title: task
        })
      }

      this.newTodo = ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
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