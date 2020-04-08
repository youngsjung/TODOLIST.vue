<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput v-on:addTodo="addTOdo"></TodoInput>
    <TodoList v-bind:propsadata="todoItems"></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
export default{
  data(){
    return {
      todoItems : []
    }
  },
  methods: {
    addTodo(todoItem){
      localStorage.setItem(todoItem, todoItem);
      this.todoItems.push(todoItems);
    }
  },

/*
import TodoHeader from './components/TodoHeader';
import TodoInput from './components/TodoInput';
import TodoList from './components/TodoList';
import TodoFooter from './components/TodoFooter';

export default {
  */
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