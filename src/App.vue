<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput></TodoInput>
    <TodoList></TodoList>
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
  components:{
    "TodoHeader":TodoHeader,
    "TodoInput":TodoInput,
    "TodoList":TodoList,
    "TodoFooter":TodoFooter
  }
}
</script>

<style>
html,body{
  font-family: 'Noto Sans KR', sans-serif;
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
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

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
</style>
