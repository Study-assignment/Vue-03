<template>
  <div>
    <ul>
      <li v-for="item in myArr" :key="item">{{ item }}</li>
    </ul>
    <button @click="run">走一走</button>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return { myArr: ['帅哥', '美女', '程序猿'] }
  },
  methods: {
    run() {
      // shift 删除第一个元素 ， 返回值为被删除的那个元素
      this.myArr.push(this.myArr.shift())
    },
  },
}
</script>
