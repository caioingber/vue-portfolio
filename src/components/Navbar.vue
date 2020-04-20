<template>
  <nav class="navbar" :class="{ open: navOpen }">
    <div class="navbar__name ">
      <router-link class="navbar__item" to="/">Caio Ingber</router-link>
    </div>
    <div class="navbar__links" :style="{}">
      <router-link to="/about">About</router-link>
      <router-link to="/projects">Projects</router-link>
      <a
        href="/assets/CaioIngber_Resume.pdf"
        target="_blank"
        class="navbar__resume"
        >Resume</a
      >
    </div>
    <div v-if="navOpen" class="navbar__ham" @click="toggle">x</div>
    <div v-else class="navbar__ham" @click="toggle">=</div>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      navOpen: false,
    };
  },
  methods: {
    toggle() {
      this.navOpen = !this.navOpen;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../global.scss";
.navbar {
  @include flex(space-between, center);
  height: 80px;
  font-size: map-get($font-sizes, medium);
  font-weight: 500;
  transition: 0.5s;
  a {
    color: $primary-color;
    text-decoration: none;
    padding-bottom: 3px;
    transition: 0.2s ease-out;

    &:hover {
      text-shadow: -0.5px -0.5px 0 $primary-color, 0.5px -0.5px 0 $primary-color,
        -0.5px 1px 0 $primary-color, 0.5px 0.5px 0 $primary-color;
      border-bottom: 1px solid $primary-color;
      transition: 0.2s ease-in;
    }
    &.router-link-exact-active {
      &:hover {
        text-shadow: -0.5px -0.5px 0 $active-color, 0.5px -0.5px 0 $active-color,
          -0.5px 1px 0 $active-color, 0.5px 0.5px 0 $active-color;
      }
      color: $active-color;
      border-bottom: 2px solid $active-color;
    }
  }
  &__name {
    margin-left: map-get($margins, large);
  }
  &__links {
    margin-right: map-get($margins, large);
    a {
      margin: 0 map-get($margins, small);
    }
  }
  &__ham {
    position: absolute;
    top: 20px;
    right: 2rem;
    display: none;
    cursor: pointer;
  }
}
@include tablet {
  .open {
    height: 250px;
    transition: 0.5s;
  }
  .navbar {
    overflow: hidden;
    @include flex(flex-start, flex-start, column);
    &__name {
      margin: 20px 0 40px 20px;
    }
    &__links {
      @include flex(flex-start, flex-start, column);
    }
    &__ham {
      display: block;
    }
  }
}
</style>
