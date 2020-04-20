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
              marginLeft: '-' + slidesLeft + 'vw',
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
      <contact></contact>
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
import Contact from "../components/Contact";
import Project from "../components/Project";
import "vue-awesome/icons/angle-double-right";
import "vue-awesome/icons/angle-double-left";
import Icon from "vue-awesome/components/Icon";
export default {
  name: "Projects",
  components: { Contact, Project, "v-icon": Icon },
  data() {
    return {
      currentIndex: 0,
      singleWidth: 100,
      projects: [
        {
          title: "Black Light Aquarium",
          description: "Description goes Here",
          stack: ["brands/html5", "brands/css3"],
          image: "https://i.imgur.com/7jqjeph.png",
          repo: "https://github.com/caioingber/website-mockup/",
          deployed: "https://caioingber.github.io/website-mockup/index.html",
        },
        {
          title: "BBC News Modal",
          description: "Description goes Here",
          stack: ["brands/html5", "brands/css3-alt", "brands/js"],
          image: "https://i.imgur.com/XXmX6lK.png",
          repo: "https://github.com/caioingber/bbc-news-modal",
          deployed: "https://caioingber.github.io/bbc-news-modal/",
        },
        {
          title: "SimonJS",
          description: "Description goes Here",
          stack: ["brands/html5", "brands/css3", "brands/js"],
          image: "https://i.imgur.com/HDY3jdw.png",
          repo: "https://github.com/caioingber/simon-says",
          deployed: "https://caioingber.github.io/simon-says/",
        },
        {
          title: "Python Contact Book",
          description: "Description goes Here",
          stack: ["brands/python"],
          image: "https://i.imgur.com/VFtsF4l.png",
          repo: "https://github.com/caioingber/python-contact-book",
          deployed: null,
        },
        {
          title: "Eco Country Report Card",
          description: "Description goes Here",
          stack: ["brands/react", "brands/node"],
          image: "https://i.imgur.com/7oG6Asa.png",
          repo: "https://github.com/caioingber/frontend-mern",
          deployed: "https://eco-report-card.netlify.com/",
        },
        {
          title: "Recipe Rolodex",
          description: "Description goes Here",
          stack: ["brands/react", "brands/node"],
          image: "https://i.imgur.com/SAMi7Xx.png",
          repo: "https://github.com/colleenobrien3/group-mern-frontend",
          deployed: "https://recipe-rolodex.netlify.app/",
        },
      ],
    };
  },
  computed: {
    sliderWidth() {
      return this.projects.length * this.singleWidth;
    },
    slidesLeft() {
      return this.currentIndex * this.singleWidth * 2;
    },
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
    },
  },
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
    margin: 10px;
    transition: 0.5s;

    &:hover {
      transform: scale(1.5);
      transition: 0.5s;
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
    margin-bottom: 30px;
    width: 100vw;
    overflow: hidden;
    @include flex(center, center);
  }
  &__slider {
    display: flex;
    transition: 1s ease-out;
  }
  &__nav {
    @include flex(center, center, row);
    span {
      cursor: pointer;
      margin: 1rem;
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
      transition: 0.5s ease-out;
    }
    .previous,
    .next {
      height: 1.5rem;
      &:hover {
        transform: scale(1);
      }
    }
  }
}
</style>
