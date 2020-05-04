<template>
  <div class="container">
    <Content />
  </div>
</template>

<script>
  import Content from "./Content"

  export default {
    name: "App",
    components: {
      Content
    }
  };
</script>

<style>
  .container {
    background-image: url("../assets/bg.jpg");
    height: 100%;
  }
</style>
