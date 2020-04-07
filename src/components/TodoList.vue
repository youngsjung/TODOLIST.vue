<template>
    
<section> 
<ul>
 <li v-for="(todoItem, index) in todoItems" :key="todoItem">
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