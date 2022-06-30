<template>
    <div>
      <!-- 该方法和innerHtml和innerText类似，会覆盖标签内原本内容 -->
      <div v-text="text1" v-show="isShow"></div>
      <button @click="isShow = !isShow">点击切换show</button>

      
      <div v-text="html1" v-if="isIf"></div>
      <button @click="isIf = !isIf">点击切换if</button>

      <!-- v-show是控制display：none -->
      <!-- v-if是直接是否有该dom -->
    </div>
</template>

<script>
export default {
  data(){
    return{
      text1 :"醉里挑灯看剑",
      html1 :"梦回吹角连营",
      isShow:true,
      isIf:true
    }
  }
}
</script>

<style>

</style>