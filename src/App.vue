<template>
    <div class="todo-container">
      <div class="todo-wrap">
        <TodoHeader/>
        <TodoMain :todos="todos"/>
        <TodoFooter>

        </TodoFooter>
      </div>
    </div>
</template>
<script>
  import Header from './components/Header.vue'
  import Main from './components/Main.vue'
  import Footer from './components/Footer.vue'

  export default{
    data(){
      return{
        todos:[
          {name:'吃饭', complete:false},
          {name:'睡觉', complete:false},
          {name:'写代码', complete:false}
        ]

      }
    },

    components:{
      TodoHeader:Header,
      TodoMain:Main,
      TodoFooter:Footer,
    }
  }
</script>
<style>
  /*app*/
  .todo-container {
    width: 600px;
    margin: 0 auto;
  }
  .todo-container .todo-wrap {
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
  }

</style>
