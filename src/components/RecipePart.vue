<template>
  <div class="recipe-part">
    <h3>{{ part.title }}</h3>
    <div class="recipe-text">
      <ul>
        <li v-for="(ingredient, index) in part.ingredients" :key="index">{{ ingredient }}</li>
      </ul>
      <ol>
        <li v-for="(guideline, index) in part.guidelines" :key="index">{{ guideline }}</li>
      </ol>
    </div>
  </div>
</template>

<script>
  export default {
    name: "RecipePart",
    props: {
      part: Object
    }
  };
</script>

<style scoped>
  .recipe-part {
    padding: .5em 0;
  }

  h3 {
    font-size: 1em;
    margin: 0 0 .5em 0;
  }
</style>