<template>
  <div class="container">
    <h3 class="title">{{ project.title }}</h3>
    <div class="project" @mouseenter="hoverProject" @mouseleave="hoverProject">
      <img :src="project.image" :class="{ faded: active }" />
      <div class="project__background" :class="{ project__show: active }"></div>
      <div class="project__content">
        <p class="project__description">{{ project.description }}</p>
        <p class="project__stack">
          {{ project.stack }}
        </p>
        <div>
          <a :href="project.repo" target="_blank">
            <v-icon name="brands/github-square" class="project__link" />
          </a>
          <a v-if="project.deployed" :href="project.deployed" target="_blank">
            <v-icon name="external-link-square-alt" class="project__link" />
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Icon from "vue-awesome/components/Icon";
import "vue-awesome/icons/";
export default {
  name: "Project",
  props: ["project"],
  components: { "v-icon": Icon },
  data() {
    return {
      active: false,
      imageStyle: {
        backgroundColor: `rgba(0, 0, 0, 0.413)`,
        backgroundImage: `url(${this.project.image})`,
        backgroundSize: "cover",
        backgroundRepeat: "no-repeat",
      },
    };
  },
  methods: {
    hoverProject() {
      this.active = !this.active;
      console.log(this.active);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../global.scss";
.container {
  min-width: 100vw;
  @include flex(center, center, column);
  .title {
    margin-top: 50px;
    font-size: 40px;
    font-weight: 300;
  }
}

@include large-only {
  .faded {
    transform: scale(1.2);
  }
  .project__show {
    transform: translateY(100%);
    transition: 0.3s linear;
  }
}

.project {
  border-radius: 10px;
  margin: 40px 0;
  position: relative;
  overflow: hidden;
  height: 350px;
  width: 500px;
  box-shadow: rgba(52, 43, 43, 0.55) 1px 2px 1px 2px;

  img {
    transition: 0.4s ease-in-out;
    width: 100%;
    height: 100%;
  }
  &__background {
    position: absolute;
    background-color: rgba(255, 255, 255, 0.837);
    top: -100%;
    height: 100%;
    width: 100%;
    transition: 0.3s linear;
  }

  @include flex(center, center, column);
  p {
    width: 75%;
    margin-bottom: 20px;
  }
  &__description {
    text-align: left;
    font-size: 20px;
  }
  &__stack {
    font-size: 16px;
    font-weight: 600;
  }
  &__content {
    @include flex(center, center, column);
    height: 100%;
    width: 100%;
    position: absolute;
    opacity: 0;
    &:hover {
      opacity: 1;
      transition: 0.5s;
    }
  }

  svg {
    transform: scale(0.6);
  }
  &__link {
    cursor: pointer;
    transition: 0.1s ease-out;
    &:hover {
      transform: scale(0.7);
      transition: 0.1s ease-in;
    }
  }
}

@include tablet {
  .project {
    height: 250px;
    width: 400px;
    &__background {
      top: 0;
    }
    &__content {
      opacity: 1;
      transition: 0.5s;
    }
  }
}
@include mobile {
  .project {
    width: 250px;
    height: 300px;
  }
  .container {
    .title {
      font-size: 30px;
    }
  }
}
</style>
