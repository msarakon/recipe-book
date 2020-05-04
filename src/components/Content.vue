<template>
  <div class="content">
    <div class="heading">EVOL Recipes ❤️ cooking with LOVE</div>
    <img class="header" src="../assets/header.jpg" alt="Header" />
  </div>
</template>

<script>
  export default {
    name: "Content"
  };
</script>

<style>
  :root {
    --border-color: #A87A4C;
  }

  .heading {
    font-family: "Trebuchet MS", sans-serif;
    font-size: 1.2em;
    text-align: center;
    margin-bottom: 1em;
  }

  .content {
    box-sizing: border-box;
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
  }
</style>
