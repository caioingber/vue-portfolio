<template>
  <div class="projects">
    <button>prev</button>
    <div class="projects__slider">
      <project
        v-for="project in projects"
        :key="project"
        :project="project"
      ></project>
    </div>
    <button>next</button>
  </div>
</template>

<script>
import Project from "../components/Project";
export default {
  name: "Projects",
  components: { Project },
  data() {
    return {
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
  methods: {
    name() {}
  }
};
</script>

<style lang="scss" scoped>
@import "../global.scss";

.projects {
  height: 60vh;
  @include flex(center, center);
  &__slider {
    display: flex;
    width: 400px;
    overflow: hidden;
  }
}
</style>
