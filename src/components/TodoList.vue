<template>
    
<section> 
<ul>
 <li v-for="(todoItem, index) in propsdata" :key="todoItem">
      {{todoItem }}
     <button v-on:click="removeTodo(todoItem, index)"> 삭제 </button>
 </li>
</ul>
</section>



</template>


<script>
export default {
    data(){
        return{
            todoItems: []
        };
    },
    created(){
        if(localStorage.length > 0){
            for(var i =0; i < localStorage.length; i++){
                this.todoItems.push(localStorage.key(i));
            }
        }
    },
    props:['propsdata'],
     methods: {
        removeTodo(todoItem, index){
        localStorage.removeItem(todoItem);
        this.todoItems.splice(index, 1);
        }
    }
    
};

</script>

<style >

</style>