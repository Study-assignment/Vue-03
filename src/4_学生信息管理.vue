<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input
        type="text"
        v-model.trim="userInfo.name"
        placeholder="请输入姓名"
      />
    </div>
    <div>
      <span>年龄:</span>
      <input
        type="number"
        v-model.number="userInfo.age"
        placeholder="请输入年龄"
      />
    </div>
    <div>
      <span>性别:</span>
      <select v-model="userInfo.sex">
        <option :value="1">男</option>
        <option :value="0">女</option>
      </select>
    </div>
    <div>
      <button @click="addFn">{{ flag ? '修改' : '添加' }}</button>
    </div>
    <div>
      <table border="1" cellpadding="10" cellspacing="0">
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
          <td>{{ { 0: '女', 1: '男' }[item.sex] }}</td>
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
  name: 'App',
  data() {
    return {
      flag: 0,
      userInfo: {
        name: '',
        age: '',
        sex: 1,
      },
      list: [
        { id: 1, name: '张三', age: 20, sex: 1 },
        { id: 2, name: '李四', age: 22, sex: 1 },
        { id: 3, name: '韩梅梅', age: 19, sex: 0 },
      ],
    }
  },
  methods: {
    addFn() {
      if (!this.flag) {
        // 添加
        if (this.name == '' || this.age == '') return alert('请输入完整')
        this.list.push({
          id: this.list.length ? this.list[this.list.length - 1].id + 1 : 1,
          ...this.userInfo,
        })
      } else {
        // 修改
        const index = this.list.findIndex((item) => item.id == this.flag)
        this.$set(this.list, index, {
          id: this.flag,
          ...this.userInfo,
        })
        alert('修改完成')
        this.flag = 0
      }
      this.userInfo.name = ''
      this.userInfo.age = ''
      this.userInfo.sex = 1
    },
    del(id) {
      const index = this.list.findIndex((item) => item.id == id)
      this.list.splice(index, 1)
    },
    edit(item) {
      this.userInfo.name = item.name
      this.userInfo.age = item.age
      this.userInfo.sex = item.sex
      this.flag = item.id
    },
  },
}
</script>
