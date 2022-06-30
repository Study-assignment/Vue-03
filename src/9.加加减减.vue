<template>
  <div id="app">
    <ul>
      <li v-for="(item,index) in arr" :key="index">
        {{item}}
        <button @click="remove(index)">删除</button>
      </li>
    </ul>
    <button @click="add">生成</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr:[1,2,3]
    };
  },
  methods: {
    add(){
      this.arr.push(Math.floor(Math.random()*10))
    },
    remove(index){
      this.arr.splice(index,1)
    }
  },
};
</script>