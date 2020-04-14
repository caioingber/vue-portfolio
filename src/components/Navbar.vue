<template>
  <nav class="navbar">
    <div class="navbar__name ">
      <router-link class="navbar__item" to="/">Caio Ingber</router-link>
    </div>
    <div class="navbar__links">
      <router-link class="navbar__item" to="/">Resume</router-link>
      <router-link class="navbar__item" to="/about">About</router-link>
      <router-link class="navbar__item" to="/projects">Projects</router-link>
      <router-link class="navbar__item" to="/contact">Contact</router-link>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar"
};
</script>

<style lang="scss" scoped>
@import "../global.scss";
.navbar {
  @include flex(space-around);
  height: 100px;
  &__item {
  }

  .router-link-active {
    color: $primary-color;
    text-decoration: none;
  }
}
</style>
