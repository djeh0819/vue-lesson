<template>
  <div>
    <h1>{{ count }}</h1>
    <button @click="count += 1">click</button>
    <h2 v-if="count % 2 === 0">Even</h2>
    <h2 v-if="count % 2 != 0">Odd</h2>

    <input v-model="username" />
    <h2> {{username}} </h2>
    <ol>
     <li v-for="text in list" :key="text">
       {{text}}
     </li>
    </ol>
  </div>
</template>

<script>
export default {
  data() {
    return { 
      count: 0,
      list: [
        'Learn JavaScript',
        'Learn Vue',
        '$ Profit$',
      ],
      username: '',
      };
  },
};
</script>

<style>
div {
  color: purple;
}
</style>