<template>
  <div>
    <ul>
      <li v-for="(item, index) in arr" :key="index">{{ item }}</li>
    </ul>
    <button @click="reverse">数组翻转</button>
    <button @click="slice">截取前3个</button>
    <button @click="change">更新第一个元素值</button>
    <button @click="addVal">在0上添加一个值</button>
  </div>
</template>

<script>
export default {
  name: 'App',

  data() {
    return {
      arr: [1, 2, 3, 4, 5],
    }
  },
  methods: {
    reverse() {
      this.arr.reverse()
    },
    slice() {
      this.arr = this.arr.slice(0, 3)
    },
    change() {
      this.$set(this.arr, 0, 1000)
    },
    addVal() {
      this.arr.splice(0, 0, 50)
    },
  },
}
</script>

<style scoped></style>
