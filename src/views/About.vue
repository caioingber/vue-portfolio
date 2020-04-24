<template>
  <div class="about">
    <div class="about__left">
      <img src="../pictures/GA13Feb_Linked-5.jpg" alt="" />
      <contact></contact>
    </div>
    <div class="about__right">
      <div class="about__content">
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
        <p>
          <strong>Front-end:</strong> HTML/CSS, Sass, Javascript, React, Vue
        </p>
        <p>
          <strong>Back-end:</strong> Node, Express, Python, Django, MongoDB,
          PostgreSQL
        </p>
        <p>
          <strong>Management/Deployment:</strong> Git, Heroku, NPM, Pip/Pipenv
        </p>
      </div>
      <div class="about__links">
        <router-link to="/projects" class="button">Projects</router-link>
      </div>
    </div>
  </div>
</template>

<script>
import Contact from "../components/Contact";
export default {
  components: { Contact },
};
</script>

<style lang="scss" scoped>
@import "../global.scss";

.about {
  margin-top: 5rem;
  @include flex(center, flex-start);
  img {
    height: 225px;
    width: 225px;
    border-radius: 100%;
    margin-right: 1rem;
    border: 1.5px solid $primary-color;
  }
  @include large-only {
    &__left {
      margin-right: 3rem;
    }
  }
  &__right {
    @include flex(center, flex-start, column);
    width: 40%;
    p {
      text-align: justify;
      line-height: 1.5;
      // margin-bottom: 1rem;
    }
    h3 {
      font-size: map-get($font-sizes, medium);
      font-weight: 300;
      text-align: left;
      margin: 2rem 0 0.5rem 0;
    }
  }

  &__links {
    margin: 2rem 0 4rem 0;
  }
}
@include tablet {
  .about {
    @include flex(center, center, column);
    &__right {
      width: 80%;
    }
    &__links {
      align-self: center;
    }
  }
}
</style>
