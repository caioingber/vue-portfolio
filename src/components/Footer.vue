<template>
  <footer>
    Caio Ingber &copy; 2020
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style lang="scss" scoped>
@import "../global.scss";

footer {
  width: 100%;
  position: absolute;
  bottom: 0;
  text-align: left;
  padding: 1% 2%;
}
@include large-only {
  footer {
    position: absolute;
    bottom: 0;
  }
}
@include tablet {
  footer {
    margin-top: 0.5rem;
    padding: 2% 5%;
  }
}
</style>
