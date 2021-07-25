<template>
  <div id="app">
    <DisplayData></DisplayData>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import DisplayData from "./components/DisplayData.vue";
@Component({
  components: {
    DisplayData,
  },
})
export default class App extends Vue {}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: whitesmoke;
  padding-top: 5px;
}
</style>
