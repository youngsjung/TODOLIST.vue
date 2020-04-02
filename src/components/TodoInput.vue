<template>
  <div>
    <input type="text" v-model="newTodoItem" />
    <button v-on:click="addTodo">추가</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodoItem: ''
    };
  },

  methods: {
    addTodo() {
      //  console.log(this.newTodoItem);// 뷰 인스턴스에서 값을 인식할 수 있게 해주는 newTodoItem
      //localStorage.setItem(this.newTodoItem,this.newTodoItem);
      //값이 빈 값인지 체크 빈 값이 아니면 로직 수행
      if (this.newTodoItem !== '') {
        var value = this.newTodoItem && this.newTodoItem.trim();
        localStorage.setItem(value, value);

        this.clearInputbox(); // 다른 methods를  호출 하고 싶으면 this를 넣어야 합니다.
      }
    },
    clearInputbox() {
      this.newTodoItem = '';
    }
  }
};
</script>
<style></style>
