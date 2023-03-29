<template>
  <button @click="show = !show">Menu</button>
  <transition name="fade">
    <Menu v-show="show" />
  </transition>

  <div>
    <Modal />
  </div>
  <div>{{ text }}</div>
  <div>{{ algo }}</div>

  <UserRepositories :user="'Rodrigo'"></UserRepositories>
  <Home></Home>
  <HomeTwo></HomeTwo>
</template>

<script>
import Menu from "./components/Menu.vue";
import Modal from "./components/Modal.vue";
import base from '@/mixins/base';
import UserRepositories from './components/UserRepositories'
import Home from "./components/Home.vue";
import HomeTwo from "./components/HomeTwo.vue";
export default {
  name: "App",
  components: { Menu, Modal, UserRepositories, Home, HomeTwo },
  mixins: [base],
  data() {
    return {
      show: false,
      text: "Hola Vue",
    };
  },
  beforeCreate() {
    console.log('beforeCreate', this.$data, this.$el);
  },
  created() {
    console.log('created', this.$data, this.$el);
  },
  mounted() {
    console.log('mounted', this.$data, this.$el);
  },
};
</script>
<style>
#app {
  font-family: Arial, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}
</style>
