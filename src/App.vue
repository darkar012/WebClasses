<script>
import ToDoList from "./components/ToDoList.vue";
import Modal from "./components/modal.vue";
export default {
  components:{
    ToDoList,
    Modal
},
data(){
  return {
    showModal:false
  }
},
methods:{
  openModal(){
    this.showModal = true;
  },
  closeModal(){
    this.showModal = false;
  }
}
}
</script>

<template>
  <header>
    <h2>To Do List</h2>
  </header>

  <main>
    <ToDoList />
    <button @click="openModal">Abrir Modal</button>
    <Modal v-if="showModal" @close="closeModal"></Modal>
  </main>
</template>

<style scoped>

header{
  width: 100%;
  background-color:blueviolet;
  color:white;
  text-align:center;
}

h2{
  text-align:center;
}


</style>
