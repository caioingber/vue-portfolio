<template>
  <div class="home">
    <h1>Caio Ingber</h1>
    <h2>Software Engineer</h2>
    <div class="home__links">
      <router-link to="/about" class="button">About Me</router-link>
      <a href="/assets/Caio_Ingber_Resume.pdf" target="_blank" class="button"
        >Resume</a
      >
    </div>
    <contact></contact>
  </div>
</template>

<script>
import Contact from "../components/Contact";
export default {
  name: "Home",
  components: { Contact },
};
</script>

<style lang="scss" scoped>
@import "../global.scss";

.home {
  margin: 5rem 0 0 20%;
  @include flex(flex-start, flex-start, column);
  h1,
  h2 {
    font-weight: 300;
    text-align: left;
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
  &__links {
    margin-left: 1rem;
  }
}

@include mobile {
  .home {
    margin: 5rem 0 0 10%;
    h1 {
      font-size: 3rem;
    }
    h2 {
      font-size: 1.5rem;
    }
  }
}
</style>
