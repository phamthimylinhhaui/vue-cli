<template>
  <img v-if="isShowHeader" alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld
    v-if="isShowHeader"
    ref="componentHello"
    msg="Welcome to Your Vue.js App"
  />
  <teleport to="body">
    <header-app
      v-if="isShowHeader"
      ref="header"
      menu="new menu from app"
      content="this is content"
      theme="contact"
      @cancel="onToggleHeader"
    >
      <template v-slot:header>
        <h2>this is sub header</h2>
      </template>
      <template v-slot:footer>
        <h2>this is sub footer</h2>
        <div class="d-flex">
          <button @click="onToggleHeader">close</button>
        </div>
      </template>
      <h4>this is sub content</h4>
    </header-app>
  </teleport>
  <button v-if="isShowHeader" @click="onToggleHeader">Toggle header</button>
  <h1 v-if="isShowHeader" class="header">hello vue cli</h1>
  <button v-if="isShowHeader" @click="onChange">click on log</button>

  <quiz-form />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/Header.vue";
import QuizForm from "@/components/QuizForm.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    HeaderApp: Header,
    QuizForm,
  },
  data() {
    return {
      isShowHeader: false,
    };
  },
  methods: {
    onChange() {
      console.log("hello");
      console.log(this.$refs.componentHello);
      console.log("header:", this.$refs.header);
      this.$refs.componentHello.methodTesting();
    },
    onToggleHeader() {
      console.log("23423");
      this.isShowHeader = !this.isShowHeader;
    },
  },
};
</script>
