<template>
  <div>
    <p v-bind:style="{ color: 'red', fontSize: '100px' }">asdasd</p>
    <p v-bind:style="{ color: colorColor, fontSize: `${fontSize}px` }">
      asdasd
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      colorColor: 'green',
      fontSize: 100,
    }
  },
}
</script>

<style></style>
