<script>
export default {
    props:{
        tittle:String,
        showButton:Boolean,
        titleColor:String
    },
  methods: {
    click() {},
    cerrarModal(){
        this.$emit('close')
    }
  }, computed:{
    tittleClass(){
        return `title--${this.titleColor}`
    }
  }
};
</script>
<template>
  <div class="backdrop" @click.self="cerrarModal">
    <aside class="modal-container">
      <h1 :class="tittleClass">{{tittle}}</h1>
      <slot></slot>
      <button @click="cerrarModal" v-if="showButton">cerrar</button>
      <slot name="links"></slot>
    </aside>
  </div>
</template>
<style>

.title--purple{
color:purple;
}

.title--blue{
color:blue;
}

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
