<template>
  <div class="home">
    <h1>Caio Ingber</h1>
    <h2>Software Engineer</h2>
    <div class="home__links">
      <router-link to="/about">About Me</router-link>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  components: {},
};
</script>

<style lang="scss" scoped>
@import "../global.scss";

.home {
  margin: 5rem 0 0 20%;
  @include flex(center, flex-start, column);
  justify-self: center;
  h1,
  h2 {
    font-weight: 300;
  }

  h1 {
    font-size: 5rem;
    margin-bottom: 1rem;
  }
  h2 {
    font-size: 2rem;
    margin-bottom: 1.5rem;
    margin-left: 1rem;
  }
  a {
    text-decoration: none;
    padding: 10px;
    border: 1px solid $primary-color;
    transition: 0.25s ease-out;
    margin-left: 1rem;
    &:hover {
      color: #fff;
      background-color: $primary-color;
      transition: 0.25s ease-in;
    }
  }
}
</style>
