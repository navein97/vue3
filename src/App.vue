<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome NAVEIN !!!" /> -->
  <SampleComposition />
  <ExampleRef />
</template>

<script>
//import HelloWorld from "./components/HelloWorld.vue";
import SampleComposition from "./components/SampleComposition.vue";
import ExampleRef from "./components/ExampleRef.vue";

export default {
  name: "App",
  components: {
    //HelloWorld,
    SampleComposition,
    ExampleRef,
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
