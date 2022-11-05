<template>
  <div>
    <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo" />
    <!-- <button v-on:keyup.enter="addTodo">+</button> -->
    <button v-on:click="addTodo">+</button>
    <!-- v-on:keyup.enter == @keyup.enter -->
  </div>
</template>

<script>
export default {
  data : function() {
    return {
      newTodoItem: ""
    }
  },
  methods: {
    addTodo: function() {
      console.log(this.newTodoItem);
      // 저장하는 로직
      localStorage.setItem(this.newTodoItem, this.newTodoItem);
      // this.newTodoItem = '';
      this.clearInput();
    },
    clearInput: function() {
      this.newTodoItem = '';
    }
  }
}
</script>

<style scopped>
input:focus {
  outline: none;
}

</style>