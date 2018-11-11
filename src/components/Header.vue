<template>
  <div class="todo-header">
    <input type="text" placeholder="请输入你的任务名称，按回车键确认" @keyup.enter="add" v-model="name"/>
  </div>
</template>
<script>
  export default{
    props:{
      addTodo:{
        type:Function,
        require:true
      }
    },
    data(){
      return{
        name:''
      }
    },
    methods:{
      add(){
     //根据输入的数据，封装一个todo对象
    const name=this.name.trim()
    if(!name){
      return alert('必须输入')
    }
    const  todo={
      name,
      complete:false
    }
    //调用addTodo（）添加todo
    this.addTodo(todo)
    //清除输入
    this.name=''
      }
    }
  }
</script>
<style scoped>
  /*header*/
  .todo-header input {
    width: 560px;
    height: 28px;
    font-size: 14px;
    border: 1px solid #ccc;
    border-radius: 4px;
    padding: 4px 7px;
  }

  .todo-header input:focus {
    outline: none;
    border-color: rgba(82, 168, 236, 0.8);
    box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 8px rgba(82, 168, 236, 0.6);
  }

</style>
