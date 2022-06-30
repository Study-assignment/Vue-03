<template>
  <div>
    <div
      v-for="(item, index) in arr"
      :key="index"
      style="display: inline-block"
    >
      <input type="checkbox" :value="item" v-model="num" /> {{ item }}
      &nbsp;
    </div>
    <p>你选中的元素, 累加的值和为: {{ theSum }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num: [],
      arr: [9, 15, 19, 25, 29, 31, 48, 57, 62, 79, 87],
    }
  },
  computed: {
    theSum() {
      return this.num.reduce((pre, item) => pre + item, 0)
    },
  },
}
</script>

<style></style>
