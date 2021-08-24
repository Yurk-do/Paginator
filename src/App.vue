<template>
  <div id="app">
    <h1>List countries</h1>
    <PaginationComponent :itemsList="this.countryList" :limit="5"></PaginationComponent>
  </div>
</template>

<script>
import { countryList } from "./services/countries.js";
import PaginationComponent from "./components/PaginationComponent.vue";
export default {
  name: "App",
  components: {
    PaginationComponent,
  },
  data() {
    return {
      countryList,
    };
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
  margin-top: 100px;
  font-size: 40px;
}
</style>
