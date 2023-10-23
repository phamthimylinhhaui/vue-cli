<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld ref="componentHello" msg="Welcome to Your Vue.js App" />
  <header-app
    ref="header"
    menu="new menu from app"
    content="this is content"
    theme="contact111"
  />
  <h1 class="header">hello vue cli</h1>
  <button @click="onChange">click on log</button>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/Header.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    HeaderApp: Header,
  },
  data() {
    return {};
  },
  methods: {
    onChange() {
      console.log("hello");
      console.log(this.$refs.componentHello);
      console.log("header:", this.$refs.header);
      this.$refs.componentHello.methodTesting();
    },
  },
};
</script>
