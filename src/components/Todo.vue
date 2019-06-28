<template>
  <!--1{{index}}-{{todo}}-->
  <!--2-->
  <!--<li v-for="todo in todos">{{todo}}</li>-->
  <!--3 <li>Walk the Dogs</li> <li>Walk the Dogs</li><li>Walk the Dogs</li>-->
  <ul>
    <li v-for="(todo, index) in todos" :key="index" @click="todoDone(index)">{{ todo }}</li>
  </ul>
</template>
<script>
export default {
  props: {
    //matche the name of parent vue <Todo :todos="todoList"/>
    todos: {
      type: Array,
      required: true
    }
  },
  /*---0621start----*/
  methods: {
    todoDone(index) {
      console.log(index);
      //$emit emits an event from the child component to the parent component
      this.$emit("removeTodo", index);
    }
  }
};
</script>
