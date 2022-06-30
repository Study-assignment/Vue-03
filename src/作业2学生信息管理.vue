<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model.trim="name" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model.trim="age" />
    </div>
    <div>
      <span>性别:</span>
      <select v-model="sex">
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click="addFn">添加/修改</button>
    </div>
    <div>
      <table>
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>性别</th>
          <th>操作</th>
        </tr>
        <tr v-for="item in list" :key="item.id">
          <td>{{ item.id }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.age }}</td>
          <td>{{ item.sex }}</td>
          <td>
            <button @click="del(item.id)">删除</button>
            <button @click="edit(item)">编辑</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isFlag: true,
      name: '',
      age: 0,
      sex: '',
      id: '',
      list: [
        { id: 1, name: 'Tom2', age: 25, sex: '女' },
        { id: 2, name: 'Jone', age: 21, sex: '女' },
        { id: 3, name: '小李', age: 18, sex: '男' },
      ],
    }
  },
  methods: {
    addFn() {
      if (this.isFlag && this.list.some((item) => item.name == this.name))
        return alert('名字重复')
      if (this.isFlag) {
        if (!this.name || !this.age || !this.sex)
          return alert('有值才能增加新数据')
        const id = this.list.length + 1
        this.list.push({ id, name: this.name, age: this.age, sex: this.sex })
        this.name = ''
        this.sex = ''
        this.age = 0
      } else {
        const index = this.list.findIndex((ele) => ele.id === this.id)
        this.list.splice(index, 1, {
          id: this.id,
          name: this.name,
          age: this.age,
          sex: this.sex,
        })
        this.name = ''
        this.sex = ''
        this.age = 0
        this.isFlag = true
      }
    },
    edit(item) {
      this.name = item.name
      this.age = item.age
      this.sex = item.sex
      this.id = item.id
      this.isFlag = false
    },
    del(id) {
      const index = this.list.findIndex((ele) => ele.id === id)
      this.list.splice(index, 1)
    },
  },
}
</script>
<style>
th,
td {
  padding: 5px;
  border: 1px solid black !important;
  text-align: center;
}
td button:nth-child(1) {
  margin-right: 10px;
}
</style>
