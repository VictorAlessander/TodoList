<template>
  <div class="todolist">
    <input type="text" v-model="newTodo.title" style="width: 400px;">
    <input type="submit" class="button button-outline" @click="addTodo()" value="Add Task"></input>
    <ul style="padding: 0; list-style-type: none;">
      <li v-for="todo in todos" style="display: inline-block; margin: 0 10px;">
        <label v-bind:class="{done: todo.completed}">{{ todo.title }} <input type="checkbox" v-model="todo.completed"></label>
        <button @click="removeTodo(todo)" class="button-small">Remove</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'TodoList',

  data () {
    return {
      newTodo: {
        title: '',
        completed: false
      },

      todos: []
    }
  },

  methods: {
    addTodo: function () {
      var taskTitle = this.newTodo.title.trim()
      var taskCompleted = this.newTodo.completed

      if (taskTitle) {
        this.todos.push({
          title: taskTitle,
          completed: taskCompleted
        })
      }

      this.newTodo.title = ''
      this.newTodo.completed = false
    },

    removeTodo: function (task) {
      var index = this.todos.indexOf(task)
      this.todos.splice(index, 1)
    }
  }
}
</script>

<style type="text/css">

  /* Custom size */
  .button-small {
    font-size: .8rem;
    height: 2.8rem;
    line-height: 2.8rem;
    padding: 0 1.5rem;
  }

  label.done {
    color: #d9d9d9;
    text-decoration: line-through;
  }

</style>