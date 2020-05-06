<template>
  <div class="recipe">
    <div class="recipe-title" @click="open = !open">
      {{ recipe.title }}
    </div>
    <div class="recipe-togglable" :class="{ hidden: !open }">
      <div class="recipe-content">
        <div class="recipe-text">
          <ul v-if="!!recipe.ingredients">
            <li v-for="(ingredient, index) in recipe.ingredients" :key="index">
              {{ ingredient }}
            </li>
          </ul>
          <ol v-if="!!recipe.guidelines">
            <li v-for="(guideline, index) in recipe.guidelines" :key="index">
              {{ guideline }}
            </li>
          </ol>
          <RecipePart
            v-for="(part, index) in recipe.parts"
            :key="index"
            :part="part"
          />
        </div>
        <img
          v-if="!!recipe.image"
          :src="images[recipe.image]"
          :title="recipe.title"
          :alt="recipe.title"
          class="recipe-image"
        />
      </div>
    </div>
  </div>
</template>

<script>
import images from "../assets/recipes/*.png";
import RecipePart from "./RecipePart";

export default {
  name: "Recipe",
  components: {
    RecipePart,
  },
  props: {
    recipe: Object,
  },
  data: () => ({
    open: false,
    images,
  }),
};
</script>

<style>
.recipe {
  --border-color: rgba(0, 0, 0, 0.1);
  border-radius: 0.3em;
  background-color: rgba(0, 0, 0, 0.04);
  border: 1px solid var(--border-color);
  box-shadow: 0px 0px 6px 0px var(--border-color);
}

.recipe-title {
  font-size: 1.2em;
  font-family: "Trebuchet MS", sans-serif;
  font-weight: bold;
  letter-spacing: 1px;
  padding: 0.7em 1em;
}

.recipe-title:hover {
  cursor: pointer;
  color: #d42a5a;
  background-color: rgba(0, 0, 0, 0.02);
}

.recipe-togglable {
  height: auto;
  transform: scaleY(1);
  transform-origin: top;
  transition: transform 0.3s ease-out;
  overflow: hidden;
}

.recipe-togglable.hidden {
  transform: scaleY(0);
}

.hidden .recipe-content {
  display: none;
}

.recipe-content {
  padding: 1em;
  display: grid;
  grid-template-columns: 2fr 1fr;
}

.recipe-content ul,
ol {
  margin: 0;
  padding: 0 0 0 1em;
  float: left;
}

.recipe-content ul {
  list-style-type: square;
}

.recipe-content li {
  padding: 0.3em;
}

.recipe-text {
  display: grid;
  grid-template-rows: auto;
  grid-row-gap: 1em;
}
</style>
