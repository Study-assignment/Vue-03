<template>
  <div>
    <p>请选择你要购买的书籍</p>
    <ul>
      <li v-for="(item, ind) in arr" :key="ind">
        {{ item['name'] }}
        <button @click="buyFn(ind)">买书</button>
      </li>
    </ul>
    <table border="1px" width="500" cellspacing="0">
      <tr v-for="(item, index) in arr" :key="index">
        <th>{{ index + 1 }}</th>
        <th>{{ item['name'] }}</th>
        <th>{{ item['price'] }}</th>
        <th>{{ item['count'] }}</th>
        <th>{{ item['price'] * item['count'] }}</th>
      </tr>
    </table>
    <p>总价格为:{{ sum }}</p>
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
    };
  },
  methods: {
    buyFn(index) {
      this.arr[index]['count']++;
    },
  },
  computed: {
    sum() {
      // 数组里放的是对象, 而对象是复杂类型, 引用关系, 值改变会触发计算属性重新执行
      return this.arr.reduce((sum, obj) => {
        return (sum += obj['price'] * obj['count']);
      }, 0);
    },
  },
};
</script>
