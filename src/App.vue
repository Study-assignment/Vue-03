<template>
  <div class="div">
    <span v-for="(item,index) in arr" :key="index">
      <input type="checkbox"
        v-model="isTrue"
        :value="item"
        @change="trues"> {{item}}
    </span>
    <div>你选中的元素，所有的和加起来是:{{and}}</div>
  </div>
  
</template>

<script>
export default {
  data() {
    return {
      isTrue:[],
      arr:[9, 15, 19, 25, 29, 31, 48, 57, 62, 79, 87],
      and:0
    }
  },
  methods:{
    trues(){
     this.and= this.isTrue.reduce((req,cus)=>{
      return req+cus
      },0)
    }
  }
};
</script>
<style lang="css">
    .div{
      margin-left:550px ;
    }
</style>