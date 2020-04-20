<template>
  <div class="about">
    <p>
      I am a highly-motivated and self-starting Full Stack Software Engineer
      with a professional background in Operations. I am a natural leader with a
      track record of consistently exceeding metrics in a cross-functional
      organization. I am passionate about user-centric approaches to web
      development.
    </p>
    <div class="about__links">
      <router-link to="/about">Projects</router-link>
    </div>
    <p><em>Front-end</em>: HTML/CSS, Sass, Javascript, React, Vue</p>
    <p><em>Back-end</em>: Node, Express, Python, Django, MongoDB, PostgreSQL</p>
    <p><em>Management/Deployment</em>: HTML/CSS, Sass, Javascript</p>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../global.scss";

.about {
  @include flex(center, center, column);
  p {
    width: 30%;
    text-align: justify;
    margin-bottom: 2rem;
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
