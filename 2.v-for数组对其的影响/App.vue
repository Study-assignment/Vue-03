<template>
  <div>
    <ul>
      <!-- 循环遍历数组 -->
      <li v-for="item in arr" :key="item">{{ item }}</li>
    </ul>
    <!-- 添加点击事件，让数组翻转 -->
    <button @click="reverseFn">数组翻转</button>
    <button @click="cutFn">截取前3个</button>
    <button @click="updateFn">更新第一个元素值</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [5, 3, 9, 2, 1],
    };
  },
  methods: {
    reverseFn() {
      this.arr.reverse();
    },
    // push(),pop(),unshift(),shift(),splice(),sort(),reverce()因为可以
    //改变原数组，所以在vue中使用其修改数组，会改变页面的渲染，而filter,slice,concat不可以改变原数组，所以修改页面不会改变
    cutFn() {
      // 截取slice(开始索引，结束索引)
      this.arr = this.arr.slice(0, 3);
    },
    updateFn() {
      // this.arr[0] = 1000;//可以修改数组第一个值，但是不能渲染到页面
      // 将数组第一个数字改成1000
      this.$set(this.arr, 0, 1000);
    },
  },
};
</script>
