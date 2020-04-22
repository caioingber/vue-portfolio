<template>
  <div id="app">
    <navbar />
    <transition name="slide" mode="out-in">
      <router-view class="view" />
    </transition>
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

.slide-enter-active,
.slide-leave-active {
  transition: opacity 0.6s, transform 0.6s;
}

.slide-enter,
.slide-leave-to {
  opacity: 0;
  transform: translateX(-40%);
}
.view {
  margin-bottom: 2rem;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: $primary-color;
}
</style>
