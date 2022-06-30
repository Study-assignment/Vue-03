<template>
    <div>
      <div v-for="item in arr" :key="item">{{item}}</div>
      <button @click="fn">点击</button>
    </div>
</template>

<script>
export default {
  data(){
    return{
      arr: ["小明", "小欢欢", "大黄"],
    }
  },
  methods:{
         fn(){
          //该方法无法动态渲染
        // this.arr[3] = '小西施'

        //需要调用$set方法或者能改变原素组方法的方法
        this.$set(this.arr,3,'小西施')
      }
  }
}
</script>

<style>

</style>