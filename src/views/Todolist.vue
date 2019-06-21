<template>
  <div>
    <h1>To do list</h1>
    <!--0614-give a tag name for the list--->
    <!---0614-<Todo/>--->
    <!-----0621-listening for the event-->
    <TodoForm @newTodo="addTodo"/>
      <h2 slot="title">Add a Todo</h2>
      <p slot="desc">you are here</p>
    <!----- <ul>
        <li v-for="todo in todoList">{{todo}}</li>
      </ul>----->
    </TodoForm>
    <!-----<h4>[{titlefromParent}]</h4>---->
    <!---0621 @=@click--->
    <Todo :todos="todoList" @removeTodo="appDeleteTodo"/>
  </div>
</template>
<script>
import Todo from "@/components/Todo.vue";
//0621
import TodoForm from "@/components/TodoForm.vue";

export default {
  data() {
    return {
      todoList: ["walk the dag", "go for a ride"]
    };
  },
  components: {
    //tell we want to use and display Todo tag
    Todo,
    //0621
    TodoForm
  },
  //0621-add methods
  methods: {
    appDeleteTodo(index) {
      this.todoList.splice(index, 1);
    },
    addTodo(todo) {
      this.todoList.push(todo);
    }
  }
};
</script>

<style>
  ul {
    list-style: none;
    width:50%;
    margin: 0 auto;
  }
  ul li{
    border-bottom: 1px solid #acacac;
    padding:10px 0;
    margin-bottom:10px;
}
</style>