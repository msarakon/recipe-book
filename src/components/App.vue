<template>
  <div class="container">
    <Content />
  </div>
</template>

<script>
import Content from "./Content";

export default {
  name: "App",
  components: {
    Content,
  },
};
</script>

<style scoped>
.container {
  display: grid;
  background-image: url("../assets/bg.jpg");
  height: 100%;
}
</style>
