<template>
  <div>
    <h1>遍历数组</h1>
    <ul>
      <li v-for="(item, index) in arr" :key="index">{{ item }}</li>

      <li v-for="(item, index) in arr" :key="index">{{ item }}-{{ index }}</li>
    </ul>
    <br />

    <h1>遍历对象</h1>
    <ul>
      <li v-for="(item, index) in tObj" :key="index">{{ item }}-{{ key }}</li>
    </ul>

    <h1>遍历数字</h1>
    <ul>
      <li v-for="(item, index) in count" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'App',

  data() {
    return {
      arr: ['西亭', '江东', '秋北', '冬袅'],
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
    }
  },
}
</script>

<style></style>
