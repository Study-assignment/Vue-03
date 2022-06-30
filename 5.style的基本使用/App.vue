<template>
  <div>
    <!-- 多个命名尽量用驼峰命名方法 -->
    <h1 :style="{ color: 'red', fontSize: '100px' }">{{ msg }}</h1>
    <h1 :style="{ color: updated }">{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg: 'hello',
      updated: 'blue',
    };
  },
};
</script>

<style></style>
