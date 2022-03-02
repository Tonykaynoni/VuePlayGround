<template>
  <div id="app">
    <TonyComp />
    <Page2 />
    <Calculator />
  </div>
</template>

<script>
import TonyComp from "./components/TonyComp.vue";
import Page2 from "./components/Page2.vue";
import Calculator from "./components/Calculator.vue";

export default {
  name: "App",
  components: {
    TonyComp,
    Page2,
    Calculator,
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
