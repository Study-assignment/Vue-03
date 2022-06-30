<template>
  <div id="app">
    <ul>
      <li v-for="val in myArr" :key="val">{{ val }}</li>
    </ul>
    <button @click="btn">走一走</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      myArr: ['帅哥', '美女', '程序猿'],
    };
  },
  methods: {
    btn() {
      this.myArr.push(this.myArr[0]);
      this.myArr.shift();
    },
  },
};
</script>
