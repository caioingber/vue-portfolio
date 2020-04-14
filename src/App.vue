<template>
  <div id="app">
    <navbar />
    <router-view />
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
export default {
  components: { Navbar }
};
</script>

<style lang="scss">
@import "global.scss";

* {
  box-sizing: border-box;
  margin: 0;
  font-family: $main-font;
}

a {
  cursor: pointer;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: $primary-color;
}
</style>
