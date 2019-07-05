<template>
  <div id="testmonials">
    <h1>Testmonials</h1>
    <UserTestmonials/>
    <el-card id="form">
      <el-form ref="form" :model="form" :rules="rules" label-width="120px">
        <el-form-item label="Name" prop="name" required>
          <el-input type="text" v-model="form.name" placeholder="Your Name"></el-input>
        </el-form-item>
        <el-form-item label="Title" prop="title" required>
          <el-input type="text" v-model="form.title" placeholder="Your Position title"></el-input>
        </el-form-item>

        <el-form-item label="Comment" required>
          <el-input
            type="textarea"
            v-model="form.comment"
            laceholder="Your Comments"
            prop="comment"
          ></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="submitForm('form')">Submit</el-button>
        </el-form-item>
      </el-form>
    </el-card>
  </div>
</template>
<script>
import UserTestmonials from "@/components/UserTestmonials.vue";
export default {
  name: "testmonials",
  components: {
    //tell we want to use and display Todo tag
    UserTestmonials
  },
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
          // alert("submit!");
          alert("submit!");
        } else {
          console.log("error submit!!");
          return false;
        }
      });
    }
  }
};
</script>

<style>
#form {
  width: 60%;
  margin: 40px auto;
  padding: 20px 60px 0 0;
}
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