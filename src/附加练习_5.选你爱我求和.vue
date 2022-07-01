<template>
  <div>
    <div
      v-for="(item, index) in arr"
      style="display: inline-block"
      :key="index"
    >
      <input
        type="checkbox"
        v-model="checkNumArr"
        :value="item"
        @change="theSum"
      />
      <span>{{ item }}</span>
    </div>
    <p>你选中的元素, 累加的值和为: {{ sum }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      sum: 0,
      arr: [9, 15, 19, 25, 29, 31, 48, 57, 62, 79, 87],
      checkNumArr: [], //  保存用户选中的数字
    }
  },
  methods: {
    theSum() {
      this.sum = this.checkNumArr.reduce((sum, val) => {
        return sum + val
      }, 0)
    },
  },
}
</script>

<style></style>
