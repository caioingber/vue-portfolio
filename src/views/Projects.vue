<template>
  <div class="projects" @keyup="nextProject">
    <v-icon
      @click="nextProject"
      name="angle-double-left"
      class="previous"
      data="prev"
    />
    <div>
      <v-touch @swipeleft="leftSwipe" @swiperight="rightSwipe">
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
      </v-touch>
      <div class="projects__nav">
        <span
          v-for="(project, index) in projects"
          :key="index"
          @click="jump(index)"
          :class="[index === currentIndex ? 'active' : null]"
        >
        </span>
      </div>
    </div>
    <v-icon
      @click="nextProject"
      name="angle-double-right"
      class="next"
      data="next"
    />
  </div>
</template>

<script>
import Project from "../components/Project";
import "vue-awesome/icons/angle-double-right";
import "vue-awesome/icons/angle-double-left";
import Icon from "vue-awesome/components/Icon";
export default {
  name: "Projects",
  components: { Project, "v-icon": Icon },
  data() {
    return {
      currentIndex: 0,
      singleWidth: 100,
      projects: [
        {
          title: "Black Light Aquarium",
          description: "Description goes Here",
          stack: "Tech | Goes | Here",
          image: "https://i.imgur.com/7jqjeph.png"
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
  mounted() {
    document.addEventListener("keyup", this.nextProject);
  },
  methods: {
    leftSwipe() {
      if (this.currentIndex < this.projects.length - 1) {
        this.currentIndex++;
      }
    },
    rightSwipe() {
      if (this.currentIndex > 0) {
        this.currentIndex--;
      }
    },
    nextProject(e) {
      e.preventDefault();
      console.log(e);
      if (e.type == "click") {
        this.currentIndex++;
      }
      if (e.keyCode == 37) {
        if (this.currentIndex <= 0) {
          this.currentIndex = this.projects.length - 1;
        } else {
          this.currentIndex--;
        }
      }
      if (e.keyCode == 39) {
        if (this.currentIndex >= this.projects.length - 1) {
          this.currentIndex = 0;
        } else {
          this.currentIndex++;
        }
      }
    },
    jump(i) {
      this.currentIndex = i;
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../global.scss";

.projects {
  .previous,
  .next {
    position: relative;
    cursor: pointer;
    height: 1rem;
    &:hover {
      height: 1.5rem;
      width: auto;
      transition: 0.2s;
    }
  }
  .previous {
    left: 10%;
  }
  .next {
    right: 10%;
  }
  @include flex(center, center, row);
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
    span {
      cursor: pointer;
      margin: map-get($margins, small);
      width: 10px;
      height: 10px;
      border-radius: 100%;
      border: 1px solid $primary-color;
    }
    .active {
      background-color: $primary-color;
    }
  }
  @include tablet {
    &__slider {
      transition: 0.5s;
    }
  }
}
</style>
