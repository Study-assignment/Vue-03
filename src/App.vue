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
      <select v-model="sex" >
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click="add">添加/修改</button>
    </div>
    <div>
      <table
        border="1"
        cellpadding="10"
        cellspacing="0"
      >
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>性别</th>
          <th>操作</th>
        </tr>
        <tr v-for="item in peoples" :key="item.id">
          <td>{{item.id}}</td>
          <td>{{item.name}}</td>
          <td>{{item.age}}</td>
          <td>{{item.sex}}</td>
          <td>
            <button @click="remove(item.id)">删除</button>
            <button @click="edit(item)">编辑</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
export default {
    data(){
      return{
        peoples:[
          {
            id:1,
            name:'小西施',
            age:18,
            sex:'男'
          },
               {
            id:2,
            name:'大西施',
            age:17,
            sex:'女'
          },
              {
            id:3,
            name:'张三',
            age:20,
            sex:'女'
          }
        ],
        name:'',
        age:'',
        sex:'男',
        flag: true,
        editId:0
      }
    },
    methods:{
      //编辑确认前
      edit(item){
        this.flag=false
        this.name = item.name
        this.age = item.age
        this.sex=item.sex
        this.editId = item.id
      },
      //添加和修改
      add(){
        if(!this.name ||!this.age) return alert('姓名或者年龄不能为空')
         if(this.flag){
          //正常添加
         this.peoples.push({
          id:this.peoples[0]?this.peoples[this.peoples.length-1].id+1:1,
          name:this.name,
          age:this.age,
          sex:this.sex
        })
        this.name=''
        this.age=''
       }else{
        //编辑
        const index = this.peoples.findIndex(item=>this.editId==item.id)
        this.peoples.splice(index,1,{
          id:this.editId,
          name:this.name,
          age:this.age,
          sex:this.sex
        })
        this.name=''
        this.age=''
        this.flag=true
       }
      },
      //删除
      remove(id){
        const index = this.peoples.findIndex(item=>item.id==id)
        this.peoples.splice(index,1)
      }
    }

}
</script>

<style>
    #app{
      margin-left: 600px;
    }
</style>
