<template>
  <div class="project">
    <h3 class="project__title">{{ project.title }}</h3>
    <p class="project__description">{{ project.description }}</p>
    <p class="project__stack">{{ project.stack }}</p>
    <img :src="project.image" />
  </div>
</template>

<script>
export default {
  name: "Project",
  props: ["project"]
};
</script>

<style lang="scss" scoped>
.project {
  min-width: 100vw;
}
</style>
