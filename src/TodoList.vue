<template>
  <div>
    <input v-model="text" />
    <button @click="addTodo">Submit</button>
    <button @click="pop">Pop</button>
    <button @click="reverse">Reverse</button>
    <button @click="shift">Shift</button>
    <ul>
      <li v-for="item in list" :key="item.id" @click="toogleDone(item)">
        <input type="checkbox" v-model="item.done" />
        {{ item.text + ":  " + item.done }}
        <button @click="deleteItem(item)">delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data: () => ({
    text: "",
    list: [],
  }),
  methods: {
    toogleDone(item) {
      item.done != item.done;
    },
    addTodo() {
      if (this.text === "") return;

      const item = {
        id: Date.now(),
        text: this.text,
        done: false,
      };
      this.list.push(item);
      this.text = "";
    },
    pop() {
      this.list.pop();
    },
    reverse() {
      this.list.reverse();
    },
    shift() {
      this.list.shift();
    },
    deleteItem(item) {
      const idx = this.list.indexOf(item);
      this.list.splice(idx, 1);
    },
  },
};
</script>