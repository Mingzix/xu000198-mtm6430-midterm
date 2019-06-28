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
import axios from "axios"
export default {
  components: {
    //tell we want to use and display Todo tag
    Todo,
    //0621
    TodoForm
  },
  data() {
    return {
      todoList: []
      //---default todolist statement, can be todoList: ["my first to do."]
    };
  },
  
  //0621-add methods
  methods: {
    appDeleteTodo(index) {
      this.todoList.splice(index, 1);
    },
    addTodo(todo) {
      this.todoList.push(todo);
      axios
        .put("https://mingzix-vue-and-axios.firebaseio.com/data.json", this.todoList)
        .then(response => {
          console.log(response);
          console.log("Your data was saved status:" + response.status);
        })
        .catch(error=>{
          console.log(error);
        });
    }
  },
  /*beforeCreated(){
    console.log("before app is created");
  },
  created() {
    console.log("App is created");
  },
  beforeMount(){
    console.log("before app is mounted");
  },
  mounted(){
    console.log("App is mounted");
  },
  */
 //make sure outside methods function
 created() {
   axios
    .get("https://mingzix-vue-and-axios.firebaseio.com/data.json")
    //if it is successful
    //js function: function (response) { }
    .then(
      response => {
        // console.log(response);
          console.log(response.data);//----get array of data in console
          if(response.data){
          this.todoList = response.data;
          }
          /*-----if(response.data)
          this.todoList = response.data;
          */
        })
    .catch(error => {
      console.log("There was an error in getting data: " + error.response);
    });
 }
};//if axios request is successful, then()will run, if not catch()will run
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