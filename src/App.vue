<template>
  <div id="app">
    <navbar />
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
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

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: $primary-color;
}
</style>
