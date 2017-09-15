<template>
  <div class="todolist">
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
      todos: [
        {
          title: 'Todo A'
        },
        {
          title: 'Todo B'
        },
        {
          title: 'Todo C'
        }
      ]
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