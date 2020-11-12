<template>
  <div>
    <h1>{{ count }}</h1>
    <button @click="add">Add {{ step }}</button>
    <button @click="subtract">Subtract</button>
  </div>
</template>

<script>
export default {
  data: () => ({
    count: 1,
    step: 1,
    text: "",
  }),
  methods: {
    add() {
        this.step = this.count
      this.count += this.step;
    },
    subtract() {
      this.count -= 1;
    },
  },
};
</script>

<style>
div {
  color: purple;
}
</style>