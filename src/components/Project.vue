<template>
  <div class="project">
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
    <p>{{ project.stack }}</p>
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
  min-width: 400px;
}
</style>
