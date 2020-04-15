<template>
  <div class="container">
    <h3 class="project__title">{{ project.title }}</h3>
    <div class="project" @mouseenter="hoverProject" @mouseleave="hoverProject">
      <div v-if="active">
        <img :src="project.image" />
      </div>
      <div v-else>
        <p class="project__description">{{ project.description }}</p>
        <p class="project__stack">{{ project.stack }}</p>
      </div>

      <!-- <img :src="project.image" /> -->
    </div>
  </div>
</template>

<script>
export default {
  name: "Project",
  props: ["project"],
  data() {
    return {
      active: false,
      imageStyle: {
        backgroundColor: `rgba(0, 0, 0, 0.413)`,
        backgroundImage: `url(${this.project.image})`,
        backgroundSize: "cover",
        backgroundRepeat: "no-repeat"
      }
    };
  },
  methods: {
    hoverProject() {
      this.active = !this.active;
      console.log(this.active);
    },
    key: function(event) {
      this.message = "key " + event.key + " (" + event.keyCode + ")";
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../global.scss";
.container {
  min-width: 100vw;
  @include flex(center, center, column);
}
.project {
  @include flex(center, center, column);
  //   color: #fff;
  height: 300px;
  width: 500px;
  background-size: cover;
  background-repeat: no-repeat;

  img {
    height: 100%;
    width: 100%;
  }
}
</style>
