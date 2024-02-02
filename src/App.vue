<script>
export default
  {
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
          ],
        newTask: 'Lavatrice',
        error: false
      }
    },
    methods: {
      removeTask(index) {
        console.log('Remove task', index);
        this.toDoList.splice(index, 1);
      },
      addTask() {
        console.log("Add task");
        const obj = { text: this.newTask, done: false };
        const checkUsername = tobj => tobj.text === this.newTask;
        if (this.toDoList.some(checkUsername)) {
          this.error = 'Il compito già presente nella lista';
        }
        else if (this.newTask.length > 5) {

          this.toDoList.unshift(obj);
          this.newTask = '';
          this.error = false;
        }
        else {
          this.error = 'Il compito deve essere lungo almeno 5 caratteri'
        }
      }
    }
  }
</script>

<template>
  <h1>Lista ToDo</h1>
  <span calss="inputgrup">
    <input type="text" v-model="newTask" @keyup.enter="addTask()">
    <button @click="addTask">Aggiungi compito</button>
  </span>
  <br>
  <span>
    <div class="msgError" v-if="error">
      {{ error }}
    </div>
  </span>
  <ul>
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

<style>
i {
  font-size: 1.5rem;
  padding: 0.5rem;
}

.msgError {
  color: red;
  margin: 2rem;
  height: 1.3rem;
  font-size: 1.3rem;
}
</style>

