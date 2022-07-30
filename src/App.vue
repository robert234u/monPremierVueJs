<template>
  <h1>A faire</h1>
  <div>
    <input type="text" v-model="newTask">
    <button @click="addTask" :disabled="newTask.length < 1" >Ajouter</button>
  </div>
  <ul>
    <li v-for="task in tasks" :key="task.id">
      {{task.name}}
    </li>
  </ul>
</template>

<script>
  export default {
    data() {
      return {
        newTask: "",
        tasks: [],
        idForNewTask : 0
      }
    },
    methods: {
      addTask() {
        if (! this.newTask.trim().length) return
        this.tasks.push({
          id: this.idForNewTask,
          name: this.newTask
        });
        this.newTask = ''
      }
    }
  }
</script>