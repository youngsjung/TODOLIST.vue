<template>
  <section>
    <ul>
      <!-- 
            보간법을 사용할때 괄호를 {{ } }가 아닌 {{ }} 처럼 붙여 써야합니다.
            v-for을 사용 할 때는 key 값을 추가해 줘야 합니다.
            :key는 v-bind:key와 같은 의미 입니다. (약어로 사용한 것 입니다.)
        -->
      <li v-for="todoItem in todoItems" :key="todoItem">{{ todoItem }}</li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      todoItems: []
    };
  },
  created() {
    if (localStorage.length > 0) {
      for (var i = 0; i < localStorage.length; i++) {
        this.todoItem.push(localStorage.key(i));
      }
    }
  }
};
</script>

<style></style>
