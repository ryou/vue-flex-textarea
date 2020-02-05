<template>
  <div id="app">
    <FlexTextarea v-model="text" />
  </div>
</template>

<script>
import FlexTextarea from "./components/FlexTextarea";

export default {
  name: "app",
  components: {
    FlexTextarea
  },
  data() {
    return {
      text: ""
    };
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 20px;
  width: 320px;
  margin: 0 auto;
}
</style>
