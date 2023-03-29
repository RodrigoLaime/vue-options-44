<template>
  <div>
    <button @click="toggle">Modal</button>
    <teleport to="body">
      <div v-show="showw" class="modal">
        <h1>Titulo</h1>
        <p>Mensage</p>
        <button @click="toggle">Cerrar</button>
      </div>
    </teleport>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showw: false,
    };
  },
  methods: {
    toggle() {
      this.showw = !this.showw;
    },
  },
};
</script>
