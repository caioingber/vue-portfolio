<template>
  <div class="about">
    <img src="../pictures/GA13Feb_Linked-5.jpg" alt="" />
    <div class="about__container">
      <div class="about__info">
        <h3>About Me</h3>
        <p>
          I am a highly-motivated and self-starting Full Stack Software Engineer
          with a professional background in Operations. I am a natural leader
          with a track record of consistently exceeding metrics in a
          cross-functional organization. I am passionate about user-centric
          approaches to web development.
        </p>
      </div>
      <div class="about__skills">
        <h3>Skills</h3>
        <p><em>Front-end</em>: HTML/CSS, Sass, Javascript, React, Vue</p>
        <p>
          <em>Back-end</em>: Node, Express, Python, Django, MongoDB, PostgreSQL
        </p>
        <p><em>Management/Deployment</em>: Git, Heroku, NPM, Pip/Pipenv</p>
      </div>
      <div class="about__links">
        <router-link to="/projects">Projects</router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../global.scss";

.about {
  margin-top: 5rem;
  @include flex(center);
  img {
    height: 225px;
    width: 225px;
    border-radius: 100%;
    margin-right: 2rem;
  }
  &__container {
    @include flex(center, flex-start, column);
    width: 50%;
    p {
      text-align: justify;
      margin-bottom: 1rem;
      // margin-bottom: 2rem;
    }
  }
  &__links {
    margin: 2rem 0;
    a {
      margin-top: 2rem;
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
}
</style>
