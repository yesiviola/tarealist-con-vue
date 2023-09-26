<template>
    <div>
       <h1>Lista de Tareas</h1>
      <input v-model="newTask" @keyup.enter="addTask" placeholder="Agregar una nueva tarea">
      <ul>
        <li v-for="(task, index) in tasks" :key="index">
          {{ task }}
          <button @click="removeTask(index)">Eliminar</button>
        </li>
      </ul>
    </div>
  </template>
  
    <script>
  export default {
    data() {
      return {
        newTask: "",
        tasks: [],
      };
    },
    methods: {
      addTask() {
        if (this.newTask.trim() !== "") {
          this.tasks.push(this.newTask.trim());
          this.newTask = "";
        }
      },
      removeTask(index) {
        this.tasks.splice(index, 1);
      },
    },
  };
  </script>
  
  <style scoped>

  </style>
  