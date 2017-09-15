<template>
  <div class="todolist">
    <input type="text" v-model="newTodo.title" style="width: 400px;">
    <input type="checkbox" v-model="newTodo.completed"></input>
    <!--<button @click=addTodo()>+</button>-->
    <input type="submit" class="button button-outline" @click=addTodo() value="Add Task"></input>
    <ul v-for="todo in todos" style="padding: 0; list-style-type: none;">
      <li style="display: inline-block; margin: 0 10px;">
        {{ todo.title }}
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
    }
  }
}
</script>