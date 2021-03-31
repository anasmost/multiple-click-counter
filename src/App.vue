<template>
  <div class="container">
    <MultipleClickCounters />
  </div>
</template>
<script>
  import MultipleClickCounters from "./components/MultipleClickCounters";
  export default {
    name: "App",
    components: {
      MultipleClickCounters,
    },
  };
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  html,
  body {
    font-family: sans-serif;
  }
  pre {
    white-space: pre-wrap;
  }

  .container {
    max-width: 800px;
    margin: auto;
    padding: 1rem;
    overflow: hidden;
  }

  input {
    outline: none;
    border: none;
    display: inline-block;
    min-width: 0;
  }
  input[type="button"] {
    cursor: pointer;
  }
</style>
