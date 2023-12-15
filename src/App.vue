<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput v-on:addTodo="addTodo"></TodoInput>
    <TodoList v-bind:propsdata="todoItems"></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue';
import TodoInput from './components/TodoInput.vue';
import TodoList from './components/TodoList.vue';
import TodoFooter from './components/TodoFooter.vue';
export default {
  name: 'app',
  data(){
    return{
      todoItems:[]
    }
  },
  created(){
    if(localStorage.length > 0){
        for (var i=0; i<localStorage.length; i++){
            this.todoItems.push(localStorage.key(i));
        }
    }
  },
  components:{
    "TodoHeader":TodoHeader,
    "TodoInput":TodoInput,
    "TodoList":TodoList,
    "TodoFooter":TodoFooter
  },
  methods:{
    addTodo(todoItem){
      localStorage.setItem(todoItem,todoItem);
      this.todoItems.push(todoItem);
    }
  }
}
</script>

<style>
html,body{
  font-family: 'Noto Sans KR', sans-serif;
  font-weight:700;
  text-align:center;
  background-color:#f6f6f8;
}
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
}
img{
  vertical-align:middle;
}
#app {
  font-family: 'Noto Sans KR', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

/* h1, h2 {
  font-weight: normal;
} */

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
input{
  border-style:groove;
  width:200px;
}
button{
  border-style:groove;
}
.shadow{
  box-shadow:5px 10px 10px rgba(0,0,0,0.03);
}
</style>
