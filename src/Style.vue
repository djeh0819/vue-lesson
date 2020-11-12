<template>
  <div :class="{ list: true, red: active }">
    Hello
    <button @click="active = !active">Toogle</button>

    <h3 :style="{ background: active ? 'green' : 'red' }">World</h3>

    <input
    
        v-model="text"
    />
  </div>
</template>
<script>
export default {
  data: () => ({
    active: false,
    text: '',
  }),
};
</script>

<style scoped>
.list {
  color: green;
}
.list.red {
  color: red;
}
</style>