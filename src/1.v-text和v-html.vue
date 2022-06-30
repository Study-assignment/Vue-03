<template>
    <div>
      <!-- 该方法和innerHtml和innerText类似，会覆盖标签内原本内容 -->
      <div v-text="text1">1</div>
      <div v-text="html1">2</div>
    </div>
</template>

<script>
export default {
  data(){
    return{
      text1 :"醉里挑灯看剑",
      html1 :"梦回吹角连营"
    }
  }
}
</script>

<style>

</style>
