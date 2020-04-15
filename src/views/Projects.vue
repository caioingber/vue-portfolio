<template>
  <div class="projects">
    <h1>Projects</h1>
    <div class="projects__container">
      <div
        class="projects__slider"
        :style="{
          width: singleWidth + 'vw',
          marginLeft: '-' + slidesLeft + 'vw'
        }"
      >
        <project
          v-for="(project, index) in projects"
          :key="index"
          :project="project"
        ></project>
      </div>
    </div>
    <div class="projects__nav">
      <button @click="goToPrev">prev</button>
      <span v-for="(project, index) in projects" :key="index">
        {{ index + 1 }}
      </span>
      <button @click="goToNext">next</button>
    </div>
  </div>
</template>

<script>
import Project from "../components/Project";
export default {
  name: "Projects",
  components: { Project },
  data() {
    return {
      currentIndex: 0,
      singleWidth: 100,
      projects: [
        {
          title: "Black Light Aquarium",
          description: "Description goes Here",
          stack: "Tech | Goes | Here",
          image: "Image goes here"
        },
        {
          title: "BBC News Modal",
          description: "Description goes Here",
          stack: "Tech | Goes | Here",
          image: "Image goes here"
        },
        {
          title: "SimonJS",
          description: "Description goes Here",
          stack: "Tech | Goes | Here",
          image: "Image goes here"
        },
        {
          title: "Python Contact Book",
          description: "Description goes Here",
          stack: "Tech | Goes | Here",
          image: "Image goes here"
        },
        {
          title: "Eco Country Report Card",
          description: "Description goes Here",
          stack: "Tech | Goes | Here",
          image: "Image goes here"
        },
        {
          title: "Recipe Rolodex",
          description: "Description goes Here",
          stack: "Tech | Goes | Here",
          image: "Image goes here"
        }
      ]
    };
  },
  computed: {
    sliderWidth() {
      return this.projects.length * this.singleWidth;
    },
    slidesLeft() {
      return this.currentIndex * this.singleWidth * 2;
    }
  },
  methods: {
    goToNext() {
      if (this.currentIndex < this.projects.length - 1) {
        this.currentIndex++;
      }
      console.log(this.currentIndex);
    },
    goToPrev() {
      if (this.currentIndex > 0) {
        this.currentIndex--;
      }
      console.log(this.currentIndex);
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../global.scss";

.projects {
  @include flex(center, center, column);
  &__container {
    height: 60vh;
    width: 100vw;
    overflow: hidden;
    @include flex(center, center);
  }
  &__slider {
    display: flex;
    transition: ease-out 1s;
  }
  &__nav {
    @include flex(center, center, row);
  }
}
</style>
