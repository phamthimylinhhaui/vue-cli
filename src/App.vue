<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld ref="componentHello" msg="Welcome to Your Vue.js App" />
  <header-app ref="header" />
  <h1>hello vue cli</h1>
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

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
