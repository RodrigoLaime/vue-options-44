<template>
  <div>Hola desde home</div>
</template>

<script>
import { onMounted } from 'vue';

export default {
  setup() {
    onMounted(() => {
      console.log('Mounted!')
    });
  },
}
</script>