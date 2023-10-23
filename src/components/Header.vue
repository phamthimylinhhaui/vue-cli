<template>
  <div :class="{ 'bg-purple': theme === 'contact' }" @click="closeHeader">
    <h1 class="header">this is header component</h1>
    <h2>{{ menu }}</h2>
    <h3>{{ content }}</h3>
  </div>
</template>

<script>
export default {
  name: "header-app",
  props: {
    menu: {
      type: String,
      require: true,
    },
    content: {
      type: String,
      default: "",
    },
    theme: {
      type: String,
      default: "example",
      validator(value) {
        return ["contact", "example", "check1"].includes(value);
      },
    },
  },
  data() {
    return {};
  },
  methods: {
    closeHeader() {
      this.$emit("cancel");
    },
  },
};
</script>

<style scoped>
.header {
  background-color: darkblue;
  color: white;
}

.bg-purple {
  background-color: purple;
}
</style>
