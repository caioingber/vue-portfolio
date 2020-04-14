<template>
  <nav class="navbar">
    <div class="navbar__name ">
      <router-link class="navbar__item" to="/">Caio Ingber</router-link>
    </div>
    <div class="navbar__links">
      <a href="/assets/CaioIngber_Resume.pdf" target="_blank">Resume</a>
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
  @include flex(space-between);
  height: 100px;
  font-size: map-get($font-sizes, medium);
  font-weight: 500;
  a {
    color: $primary-color;
    text-decoration: none;
    padding-bottom: 3px;

    &:hover {
      color: $underline-color;
      border-bottom: 1px solid $underline-color;
      transition: 0.3s;
    }
    &.router-link-exact-active {
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
}
</style>
