<template>
  <div>
    <ul>
      <li v-for="(item, index) in arr" :key="index">
        {{ item }}
        <button @click="del(index)">删除</button>
      </li>
      <button @click="add">生成</button>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [1, 4, 6],
    };
  },
  methods: {
    add() {
      this.arr.push(Math.floor(Math.random() * 20));
    },
    del(index) {
      this.arr.splice(index, 1);
    },
  },
};
</script>

<style></style>
