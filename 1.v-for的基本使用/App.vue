<template>
  <div>
    <p>循环数组</p>
    <ul>
      <!-- item表示数组每个元素的值，index表示数组的索引 -->
      <li v-for="(item, index) in arr" :key="item">{{ item }},{{ index }}</li>
      <br />
      <!-- 循环数组对象里面的每个属性及对应的值 -->
      <li v-for="item in stuArr" :key="item.id">
        {{ item.id }}--{{ item.name }}--{{ item.sex }}--{{ item.hobby }}
      </li>
      <br />
      <!-- v-for遍历的对象，获得是每一项 -->
      <li v-for="item in tObj" :key="item">{{ item }}</li>
      <br />
      <!-- 遍历10这个数字的话，会遍历1-10这十个数字 -->
      <li v-for="item in count" :key="item">{{ item }}</li>
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
