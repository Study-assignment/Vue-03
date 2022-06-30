<template>
  <div>
    <p>请选择你要购买的书籍</p>
    <ul>
      <li v-for="item in arr" :key="item.name">
        {{ item.name }}
        <button @click="buyFn">买书</button>
      </li>
    </ul>
    <table border="1px" width="500" cellspacing="0">
      <tr v-for="(item, index) in arr" :key="index">
        <th>{{ index }}</th>
        <th>{{ item.name }}</th>
        <th>{{ item.price }}</th>
        <th>{{ count }}</th>
        <th>{{ sum }}</th>
      </tr>
    </table>
    <p>总价格为:</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [
        {
          name: '水浒传',
          price: 107,
          count: 0,
        },
        {
          name: '西游记',
          price: 192,
          count: 0,
        },
        {
          name: '三国演义',
          price: 219,
          count: 0,
        },
        {
          name: '红楼梦',
          price: 178,
          count: 0,
        },
      ],
      count: 0,
      sum: 0,
    };
  },
  methods: {
    buyFn() {
      
    },
  },
};
</script>
