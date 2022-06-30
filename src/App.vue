<template>
    <div>
      <span :class="{avatar:isAvatar}">我是通过动态class修改类名添加的颜色</span>
      <button @click="fn"> 点击切换类名</button>
      <br>
      <span :style="{background:'yellow',color:'skyblue'}">是通过style修改类名添加的颜色</span>

    </div>
</template>

<script>
export default {
  data(){
    return{
      isAvatar:true
    }
  },
  methods:{ 
    fn(){
      this.isAvatar = !this.isAvatar
    }
  }
}
</script>

<style>
  .avatar{
    color:red;
  }
</style>