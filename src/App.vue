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
  },
  methods: {
    removeTask(index) {
      console.log('Remove task', index);
      this.toDoList.splice(index, 1);
    }
  }
}
</script>

<template>
  <ul>
    <h1>Lista ToDo</h1>
    <li v-for="(task, index) in toDoList">
      <span :style="{ textDecoration: task.done ? 'line-through' : '' }">
        {{ task.text }}
      </span>

      <span @click="removeTask(index)">
        <i class="fa-regular fa-circle-xmark"></i>
      </span>


    </li>
  </ul>
</template>

<style></style>
