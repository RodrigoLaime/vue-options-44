<template>
  <div>{{ obj }}</div>
</template>
<script>
import { reactive, watch } from 'vue';

export default {
  setup() {
    const obj = reactive({ counter: 0 });

    setInterval(() => obj.counter++, 5000);
    watch(() => obj.counter, (valor, anterior) => {
      //muestra el log actual y el anterior
      console.log(valor, anterior);
    });

    return {
      obj,
    };
  },
};
</script>