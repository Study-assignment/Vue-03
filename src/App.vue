<template>
  <div>
    <p>循环数组</p>
    <ul>
      <!-- item表示数组每个元素的值，index表示数组的索引 -->
      <li v-for="(item, index) in arr" :key="item">{{ item }},{{ index }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: ['小明', '小欢欢', '大黄'],
      stuArr: [
        {
          id: 1001,
          name: '孙悟空',
          sex: '男',
          hobby: '吃桃子',
        },
        {
          id: 1002,
          name: '猪八戒',
          sex: '男',
          hobby: '背媳妇',
        },
      ],
      tObj: {
        name: '小黑',
        age: 18,
        class: '1期',
      },
      count: 10,
    };
  },
};
</script>

<style></style>
