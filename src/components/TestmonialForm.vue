<template>
  <el-card id="form">
    <el-form ref="form" :model="form" :rules="rules" label-width="120px">
      <el-form-item label="Name" prop="name" required>
        <el-input type="text" v-model="form.name" placeholder="Your Name"></el-input>
      </el-form-item>
      <el-form-item label="Title" prop="title" required>
        <el-input type="text" v-model="form.title" placeholder="Your Position title"></el-input>
      </el-form-item>

      <el-form-item label="Comment" prop="comment" required>
        <el-input type="textarea" v-model="form.comment" laceholder="Your Comments"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="submitForm('form')">Submit</el-button>
      </el-form-item>
    </el-form>
  </el-card>
</template>

<script>
export default {
  name: "TestmonialForm",
  data: function() {
    return {
      form: {
        name: "",
        title: "",
        comment: ""
      },
      rules: {
        name: [
          {
            required: true,
            message: "Please input your Name",
            trigger: "blur"
          },
          {
            min: 1,
            max: 50,
            message: "Length should be 1 to 50",
            trigger: "blur"
          }
        ],
        title: [
          {
            required: true,
            message: "Please input Your Position Title",
            trigger: "blur"
          },
          {
            min: 1,
            max: 50,
            message: "Length should be 1 to 50",
            trigger: "blur"
          }
        ],
        comment: [
          {
            required: true,
            message: "Please input the comment",
            trigger: "blur"
          },
          {
            min: 1,
            max: 120,
            message: "Length should be less than 120",
            trigger: "blur"
          }
        ]
      }
    };
  },
  methods: {
    submitForm(form) {
      this.$refs[form].validate(valid => {
        if (valid) {
          alert("submit!");
          // alert("submit!");

          //if (this.$emit("addList", this.form)) {
          // this.form.name = "";
          // this.form.title = "";
          // this.form.comment = "";
          //}
        } else {
          console.log("error submit!!");
          return false;
        }
      });
      axios
        .post("https://mingzi-mtm6430-midterm.firebaseio.com/data.json", form)
        .then(response => {
          //console.log(response);
          console.log("Your data was saved status:" + response.status);
          return true;
        })
        .catch(error => {
          console.log("there was an error in saving data:" + error.reponse);
        });
    }
    //addList(form) {
    // this.formList.push(formData);
    //}
  }
};
</script>
<style>
#form {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 60%;
  margin: 40px auto;
  padding: 20px 60px 0 0;
}
</style>