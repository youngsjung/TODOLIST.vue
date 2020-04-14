<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput v-on:addTodo="addTodo"></TodoInput>
    <TodoList v-bind:propsadata="todoItems" v-on:removeTodo="removeTodo"></TodoList>
    <TodoFooter v-on: removeAll="clearAll"></TodoFooter>
  </div>
</template>

<script>

import TodoHeader from './components/TodoHeader';
import TodoInput from './components/TodoInput';
import TodoList from './components/TodoList';
import TodoFooter from './components/TodoFooter';

export default{
  data(){
    return {
      todoItems : []
    }
  },
    created(){
      if(localStorage.length > 0){
        for(var i=0; i< localStorage.length; i++){
            this.todoItems.push(localStorage.key(i));
        }

      }
    },
methods: {
    addTodo(todoItem){
      localStorage.setItem(todoItem, todoItem);
      this.todoItems.push(todoItem);
    
  },
   removeTodo(){
            localStorage.removeItem(todoItem);
            this.todoItems.splice(index, 1);
  },
    clearAll(){
        localStorage.clear();
        this.todoItems = [];
    }
  },

  components: {
    'TodoHeader' : TodoHeader,
    'TodoList' : TodoList,
    'TodoInput' : TodoInput,
    'TodoFooter' : TodoFooter
  } 
}
</script>
<style >

</style>