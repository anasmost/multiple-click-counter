<template>
  <div class="clickCounter">
    <input type="button" value="CLICK HERE TO INCREMENT" @click="onClick" />
    <input :class="labelClass" type="number" :value="clickCount" disabled />
  </div>
</template>
<script>
  export default {
    name: "ClickCounter",
    data: () => ({ clickCount: 0 }),
    methods: {
      onClick() {
        this.clickCount++;
        this.$emit("iterated");
      },
    },
    computed: {
      labelClass() {
        return this.clickCount > 9 ? "label-red" : "label-black";
      },
    },
  };
</script>

<style scoped>
  .clickCounter {
    display: flex;
    flex-direction: row;
    column-gap: 2rem;
  }
  .clickCounter > input {
    min-width: 0;
    min-height: 0;
    padding: 0.5rem;
    text-align: center;
  }

  .clickCounter > input[type="button"] {
    background: #cccccc;
    box-shadow: 0 2px 2px gainsboro;
    border-radius: 4px;
  }
  .clickCounter > input[type="button"]:active {
    background: #b9b9b9;
  }
  .clickCounter > input[type="number"] {
    color: #ffffff;
    border-radius: 50%;
    width: 2rem;
  }

  .label-black {
    background: #333333;
  }
  .label-red {
    background: #ad1717;
  }
</style>
