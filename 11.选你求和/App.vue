<template>
  <div>
    <div
      v-for="(item, index) in arr"
      :key="index"
      style="display: inline-block"
    >
      <input type="checkbox" v-model="check" :value="item" />
      <span>{{ item }}</span>
    </div>
    <p>你选中的元素, 累加的值和为: {{ Sum }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [9, 15, 19, 25, 29, 31, 48, 57, 62, 79, 87],
      check: [],
    };
  },
  computed: {
    Sum() {
      return this.check.reduce((sum, val) => {
        return (sum += val);
      }, 0);
    },
  },
};
</script>

<style></style>
