<template>
  <div class="contact">
    <a href="https://github.com/caioingber" target="_blank">
      <v-icon name="brands/github-square" />
    </a>
    <a href="https://www.linkedin.com/in/caio-ingber/" target="_blank">
      <v-icon name="brands/linkedin" />
    </a>
    <a href="mailto:caioingber@gmail.com" target="_blank">
      <v-icon name="envelope-square" />
    </a>
  </div>
</template>

<script>
import Icon from "vue-awesome/components/Icon";
import "vue-awesome/icons/brands/github-square";
import "vue-awesome/icons/brands/linkedin";
import "vue-awesome/icons/envelope-square";
export default {
  name: "Contact",
  components: { "v-icon": Icon },
};
</script>

<style lang="scss" scoped>
.contact {
  margin-top: 2rem;
  a {
    margin: 0 8px;
  }
  svg {
    transform: scale(0.8);
    transition: 0.2s ease-out;
    &:hover {
      transform: scale(0.9);
      transition: 0.2s ease-in;
    }
  }
}
</style>
