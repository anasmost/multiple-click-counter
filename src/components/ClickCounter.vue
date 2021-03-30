<template>
  <div class="clickCounter">
    <input type="button" value="CLICK HERE TO INCREMENT" @click="onClick" />
    <input :class="btnClass" type="number" :value="clickCount" disabled />
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
      btnClass() {
        return this.clickCount > 9 ? "btn-red" : "btn-black";
      },
    },
  };
</script>
<style scoped>
  .clickCounter {
    display: flex;
    flex-direction: row;
    gap: 2rem;
  }
  .clickCounter > input {
    min-width: 0;
    padding: 0.5rem;
    text-align: center;
  }

  .clickCounter > input[type="button"] {
    background: blue;
    box-shadow: 0 2px 2px gainsboro;
    border-radius: 4px;
  }
  .clickCounter > input[type="button"]:active {
    background: #6262e9;
  }
  .clickCounter > input[type="number"] {
    color: #ffffff;
    border-radius: 50%;
    width: 2rem;
  }

  .btn-black {
    background: #333333;
  }
  .btn-red {
    background: #ad1717;
  }
</style>
