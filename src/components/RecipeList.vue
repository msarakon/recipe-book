<template>
  <div class="recipe-list">
    <Recipe
      v-for="(recipe, index) in recipes"
      :key="index"
      :recipe="recipe" />
  </div>
</template>

<script>
import recipes from "../data/recipes.json";
import Recipe from "./Recipe";

export default {
  name: "List",
  components: {
    Recipe,
  },
  data: () => ({
    recipes: recipes.sort((r1, r2) =>
      r1.title > r2.title ? 1 : r1.title < r2.title ? -1 : 0
    )
  })
};
</script>

<style>
.recipe-list {
  display: grid;
  grid-template-rows: auto;
  grid-row-gap: 0.5em;
}
</style>
