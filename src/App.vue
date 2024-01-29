<script>
export default {
  name: 'App',
  data() {
    return {
      toDoList:
        [
          {
            text: 'Acquistare Pane',
            done: true
          }
          ,
          {
            text: 'Acquistare Latte',
            done: false
          }
          ,
          {
            text: 'Comprare il Giornale',
            done: false
          }
        ]
    }
  }
}
</script>

<template>
  <ul>
    <h1>Lista ToDo</h1>
    <li v-for="task in toDoList">
      <span :style="{ textDecoration: task.done ? 'line-through' : '' }">
        {{ task.text }}
      </span>


    </li>
  </ul>
</template>

<style></style>
