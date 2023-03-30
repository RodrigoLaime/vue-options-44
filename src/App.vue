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
  <HomeThree></HomeThree>
  <Props first-name="Franco" last-name="Caballero"></Props>
  <Context first-name="Facundo" last-name="Figueroa" otro="algo"></Context>
  <Provide first-name="Fernando" last-name="Nogara"></Provide>
  <TemplateRefs first-name="Luquitas" last-name="Muños"></TemplateRefs>
  <OptsApi first-name="Axel" last-name="Torrico"></OptsApi>
  <ScriptSetup first-name="Marlen" last-name="Nogara"></ScriptSetup>
</template>

<script>
import Menu from "./components/Menu.vue";
import Modal from "./components/Modal.vue";
import base from "@/mixins/base";
import UserRepositories from "./components/UserRepositories";
import Home from "./components/Home.vue";
import HomeTwo from "./components/HomeTwo.vue";
import HomeThree from "./components/HomeThree.vue";
import Props from "./components/Props.vue";
import Context from "./components/Context.vue";
import Provide from "./components/Provide.vue";
import TemplateRefs from "./components/TemplateRefs.vue";
import OptsApi from "./components/OptsApi.vue";
import ScriptSetup from "./components/ScriptSetup.vue";

import { provide } from "vue";
export default {
  name: "App",
  components: {
    Menu,
    Modal,
    UserRepositories,
    Home,
    HomeTwo,
    HomeThree,
    Props,
    Context,
    Provide,
    TemplateRefs,
    OptsApi,
    ScriptSetup,
  },
  setup() {
    provide('username', 'Rodry');
  },
  mixins: [base],
  data() {
    return {
      show: false,
      text: "Hola Vue",
    };
  },
  beforeCreate() {
    /* eslint-disable */console.log(...oo_oo(`92051366_0`, 'beforeCreate', this.$data, this.$el));
  },
  created() {
    /* eslint-disable */console.log(...oo_oo(`92051366_1`, 'created', this.$data, this.$el));
  },
  mounted() {
    /* eslint-disable */console.log(...oo_oo(`92051366_2`, 'mounted', this.$data, this.$el));
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
