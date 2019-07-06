<template>
  <div id="testmonials">
    <h1>Testmonials</h1>
    <UserTestmonials/>
    <TestmonialForm @addList="addList"/>
  </div>
</template>
<script>
import UserTestmonials from "@/components/UserTestmonials.vue";
import TestmonialForm from "@/components/TestmonialForm.vue";
import axios from "axios";

export default {
  name: "testmonials",
  components: {
    //tell we want to use and display Todo tag
    UserTestmonials,
    TestmonialForm
  },
  data() {
    return {
      formList: {}
      //---default todolist statement, can be todoList: ["my first to do."]
    };
  },
  methods: {
    addList(formData) {
      //this.formList.push(formData);
    }
  },
  created() {
    // here we are making a GET request using AXIOS to get the data
    axios
      .get("https://mingzi-mtm6430-midterm.firebaseio.com//data.json")
      .then(response => {
        // console.log(response);
        // console.log(response.data);
        // Checking if the response has some data
        if (response.data) {
          this.formList = response.data;
        }
      })
      .catch(error => {
        console.log("There was an error in getting data: " + error.response);
      });
  }
};
</script>

<style>
.row {
  display: flex;
  justify-content: center;
  margin: 0 auto;
}
.box-card {
  width: 480px;
  margin: 10px;
  text-align: left;
}
</style>