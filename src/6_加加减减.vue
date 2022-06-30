<template>
  <div>
    <ul>
      <li v-for="(item, index) in arr" :key="index">
        {{ item }} <button @click="del(index)">删除</button>
      </li>
    </ul>
    <button @click="addFn">生成</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [1, 3, 5],
    }
  },
  methods: {
    addFn() {
      this.arr.push(parseInt(Math.random() * 10))
    },
    del(index) {
      this.arr.splice(index, 1)
    },
  },
}
</script>

<style></style>
