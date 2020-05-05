<template>
  <div class="content">
    <div class="heading">EVOL Recipes ❤️ cooking with LOVE</div>
    <img class="header" src="../assets/header.jpg" alt="Header" />
    <RecipeList />
  </div>
</template>

<script>
import RecipeList from "./RecipeList";

export default {
  name: "Content",
  components: {
    RecipeList,
  },
};
</script>

<style scoped>
:root {
  --border-color: #a87a4c;
}

.heading {
  font-family: "Trebuchet MS", sans-serif;
  font-size: 1.2em;
  text-align: center;
}

.content {
  background-color: #fff;
  width: 100%;
  max-width: 900px;
  margin: 0 auto;
  padding: 1em;
  height: 100%;
  box-shadow: 0px 0px 18px 0px var(--border-color);
}

.header {
  width: 100%;
  margin: 1em 0;
}
</style>
