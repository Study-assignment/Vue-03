<template>
  <div id="app">
    <table class="tb">
      <tr>
        <th>编号</th>
        <th>品牌名称</th>
        <th>创立时间</th>
        <th>操作</th>
      </tr>
      <!-- 循环渲染的元素tr -->
      <tr v-for="item in list" :key="item.id">
        <td>{{ item.id }}</td>
        <td>{{ item.name }}</td>
        <td>{{ item.time }}</td>
        <td>
          <button @click="del(item.id)">删除</button>
        </td>
      </tr>
      <tr v-if="list.length === 0">
        <td colspan="4">没有数据咯~</td>
      </tr>
    </table>
  </div>
</template>

<script>
// 1. 明确需求
// 2. 标签+样式+默认数据
// 3. 下载bootstrap, main.js引入bootstrap.css
// 4. 把list数组 - 铺设表格
// 5. 修改价格颜色
export default {
  data() {
    return {
      list: [
        { id: 100, name: '外套', price: 199, time: new Date('2010-08-12') },
        { id: 101, name: '裤子', price: 34, time: new Date('2013-09-01') },
        { id: 102, name: '鞋', price: 25.4, time: new Date('2018-11-22') },
        { id: 103, name: '头发', price: 19900, time: new Date('2020-12-12') },
      ],
    }
  },
  methods: {
    del() {
      const index = this.list.findIndex((ele) => ele.id === id)
      this.list.splice(index, 1)
    },
  },
}
</script>

<style>
#app {
  width: 600px;
  margin: 10px auto;
}

.tb {
  border-collapse: collapse;
  width: 100%;
}

.tb th {
  background-color: #0094ff;
  color: white;
}

.tb td,
.tb th {
  padding: 5px;
  border: 1px solid black;
  text-align: center;
}

.add {
  padding: 5px;
  border: 1px solid black;
  margin-bottom: 10px;
}
</style>
