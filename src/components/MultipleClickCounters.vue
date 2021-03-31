<template>
  <div>
    <h2>Multiple Counters Component</h2>
    <div class="group">
      <ClickCounter v-for="i in clickCountersCount" :key="i" @iterated="onIterated" />
    </div>
    <input type="button" value="ADD A COUNTER :)" @click="clickCounterAdd" />
    <pre v-if="clickCountersCount > 1">
      I am rendered only if there is more than one counter.
      
      The sum of all the counters is equal to <span>{{ sum }}!</span>
    </pre>
  </div>
</template>
<script>
  import ClickCounter from "./ClickCounter";
  export default {
    name: "MultipleClickCounters",
    data: () => ({
      clickCountersCount: 1,
      sum: 0,
    }),
    components: {
      ClickCounter,
    },
    methods: {
      clickCounterAdd() {
        this.clickCountersCount++;
      },
      onIterated() {
        this.sum++;
      },
    },
  };
</script>

<style scoped>
  div {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 0.2rem 0;
    gap: 1rem;
    margin: auto;
  }

  div.group {
    gap: 0;
  }

  input {
    border-radius: 4px;
    width: max-content;
  }

  input[type="button"] {
    text-transform: capitalize;
    background: #4067cf;
    color: #fefefe;
    padding: 0.5rem 1rem;
  }
  input[type="button"]:active {
    background: #4066cfb2;
  }
</style>
