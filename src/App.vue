<template>
  <div id="app">
    <navbar />
    <router-view />
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
export default {
  components: { Navbar },
};
</script>

<style lang="scss">
@import "global.scss";

* {
  box-sizing: border-box;
  margin: 0;
  font-family: $main-font;
}

.fa-icon {
  width: auto;
  height: 3rem; /* or any other relative font sizes */
}

a {
  cursor: pointer;
  color: $primary-color;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: $primary-color;
}
</style>
