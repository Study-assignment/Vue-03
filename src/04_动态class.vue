<template>
  <div>
    <p :class="{ active: isActive }" class="ppp">我是乒乒乓乓</p>

    <button @click="isActive = !isActive">点我</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: true,
    }
  },

  mounted() {},

  methods: {},
}
</script>
<style>
.active {
  color: red;
}
.ppp {
  border: 5px solid rgb(26, 223, 191);
}
</style>
