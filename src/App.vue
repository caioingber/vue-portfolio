<template>
  <div id="app">
    <navbar />
    <transition name="slide" mode="out-in">
      <router-view />
    </transition>
    <bottom />
  </div>
</template>

<script>
import Bottom from "./components/Footer";
import Navbar from "./components/Navbar";
export default {
  components: { Navbar, Bottom },
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
  height: 3rem;
}

a {
  cursor: pointer;
  color: $primary-color;
}

.slide-enter-active,
.slide-leave-active {
  transition: opacity 0.6s, transform 0.6s;
}

.slide-enter,
.slide-leave-to {
  opacity: 0;
  transform: translateX(-40%);
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  position: relative;
  text-align: center;
  color: $primary-color;
  min-height: 100vh;
}
</style>
