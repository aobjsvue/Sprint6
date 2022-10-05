<script>
  export default {
    name: "Scene",
    props: ["arrayText", "currentSentence"]
  }
</script>

<template>
  <div>
    <p v-for="(text, index) in arrayText" :key="index" :class="{active: index === currentSentence}">{{ text.txt }}</p>
  </div>
</template>

<style>
  p {
    text-align: center;
    border: 2px solid black;
    border-radius: 1.8em;
    padding: 1em;
    background-color: rgba(255, 255, 255, 0.9);
    margin: 1em;
  }
  .active {
    background-color: lightpink;
  }
  @media (min-width: 280px) and (max-width: 480px) {
    p {
      margin: 1em 0;
      font-size: small;
    }
  } 
</style>
