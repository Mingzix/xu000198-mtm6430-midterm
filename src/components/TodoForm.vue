<template>
  <div>
    <!-----default slot that information to be sent--->
    <!----<slot></slot>--->
    <slot name="title"></slot>
    <!----addTodo=addTodo method
    @submit.prevent=点击submit，添加内容到addTodo，prevent防止发送到server并阻止刷新网页-->
    <form @submit.prevent="addTodo">
      <input type="text" v-model="newTodo">
    </form>
    <!---->
    <slot name="desc"></slot>
    <br>
    <slot>Default slot, placeholder</slot>
  </div>
</template>
<script>
export default {
  data() {
    return {
      newTodo: ""
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.length) {
        this.$emit("newTodo", this.newTodo);
        this.newTodo = "";
      }
    }
  }
};
</script>
<style scoped>
input {
  min-margin: 200px;
  padding: 10px 20px;
  font-size: 1.5rem;
}
</style>