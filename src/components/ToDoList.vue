<script>
export default {
  data() {
    return {
      tasks: [
        { name: "ir a ICESI", isDone: false },
        { name: "asistir a clase", isDone: false },
        { name: "Valer Verga", isDone: false },
      ],
      showInstructions: false
    };
  },
  methods: {
    onListItemClick(task) {
      task.isDone = !task.isDone;
      console.log(this.tasks);
    },
    onListHover(task){
        console.log("encima de la tarea "+ task.name);
        this.showInstructions = true;
    },
    onListHoverOut(task){
        console.log("encima de la tarea "+ task.name);
        this.showInstructions = false;
    }
  },
  computed: {
    doneTasks() {
      return this.tasks.filter((item) => item.isDone);
    },
    unfinishedTasks() {
      return this.tasks.filter((item) => !item.isDone);
    },
  },
};
</script>
<template>
  <h3>Todas las tareas</h3>
  <ul>
    <li
      class="task"
      :class="{ 'task--selected': task.isDone }"
      v-for="task in tasks"
      :key="task.name"
      @click="() => onListItemClick(task)"
      @mouseenter="()=> onListHover(task)"
      @mouseleave="()=> onListHoverOut(task)"
    >
      {{ task.name }}
      <span v-if="task.isDone">👽</span>
      <span v-else-if="task.name.includes('ICESI')">👌</span>
      <span v-else>😂</span>
    </li>
  </ul>
  <h3>Tareas Terminadas</h3>
  <ul>
    <li
      class="task"
      :class="{ 'task--selected': task.isDone }"
      v-for="task in doneTasks"
      :key="task.name"
      @click="() => onListItemClick(task)"
    >
      {{ task.name }}
    </li>
  </ul>
  <h3>Tareas sin Terminar</h3>
  <ul>
    <li
      class="task"
      :class="{ 'task--selected': task.isDone }"
      v-for="task in unfinishedTasks"
      :key="task.name"
      @click="() => onListItemClick(task)"
    >
      {{ task.name }}
    </li>
  </ul>
  <p v-if="showInstructions">Haga click sobre una tarea para completar</p>
</template>

<style>
.task {
  color: black;
}
.task--selected {
  color: rgb(116, 116, 116);
}
</style>
