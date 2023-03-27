<template>
  <div>
    <button @click="toggle">Modal</button>
    <div v-show="show" class="modal">
      <h1>Titulo</h1>
      <p>Mensage</p>
      <button @click="toggle">Cerrar</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
    };
  },
  methods: {
    toggle() {
      this.show = !this.show;
    },
  },
};
</script>
