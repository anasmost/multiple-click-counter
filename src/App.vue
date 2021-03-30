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

  .container {
    max-width: 800px;
    margin: auto;
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
