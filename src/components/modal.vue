<script>
export default {
  methods: {
    click() {},
    cerrarModal(){
        this.$emit('close')
    }
  }
};
</script>
<template>
  <div class="backdrop" @click.self="cerrarModal">
    <aside class="modal-container">
      <h1>hola soy un modal</h1>
      <p>
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Omnis
        voluptatum vitae molestiae laborum! Eius animi harum velit deserunt
        delectus? Esse adipisci enim, natus debitis impedit explicabo voluptatum
        voluptates dolor sit.
      </p>
      <button @click="cerrarModal">cerrar</button>
    </aside>
  </div>
</template>
<style>
.backdrop {
  position: fixed;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgba(0, 0, 0, 0.5);
  width: 100vw;
  height: 100vh;
  top: 0;
  left: 0;
  bottom: 0;
}
.modal-container {
  width: 800px;
  padding: 50px;
  background-color: white;
}
</style>
