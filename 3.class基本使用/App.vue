<template>
  <div>
    <p :class="{ activeFlag }">我是p标签</p>
    <button @click="btn">点我</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeFlag: true,
    };
  },
  methods: {
    btn() {
      this.activeFlag = !this.activeFlag;
    },
  },
};
</script>

<style scoped>
.activeFlag {
  color: red;
}
.ppp {
  border: 10px solid #ccc;
}
</style>
