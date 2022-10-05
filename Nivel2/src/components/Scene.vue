<script>
  export default {
    name: "Scene",
    props: ["arrayText", "currentSentence"]
  }
</script>

<template>
  <div>
    <p v-for="(text, index) in arrayText" :key="index" :class="{active: index === currentSentence}">{{ text.story }}</p>
  </div>
</template>

<style>
  p {
    text-align: center;
    border: 2px solid black;
    border-radius: 1.8em;
    padding: 1em 0;
  }
  .active {
    background-color: lightpink;
  }
</style>
