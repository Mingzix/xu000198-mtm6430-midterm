<template>
  <el-container id="nav">
    <div id="headline">My Vue App</div>

    <el-menu
      class="el-menu-demo"
      mode="horizontal"
      background-color="#1b1b1b"
      text-color="#fff"
      active-text-color="#ffd04b"
    >
      <el-menu-item index="1">
        <router-link :to="{ name: 'home'}">Home</router-link>
      </el-menu-item>
      <el-menu-item index="2">
        <router-link :to="{ name: 'about'}">About</router-link>
      </el-menu-item>
      <el-menu-item index="3">
        <router-link :to="{ name: 'contact'}">Contact</router-link>
      </el-menu-item>
      <el-menu-item index="4">
        <router-link :to="{ name: 'testmonials'}">Testmonials</router-link>
      </el-menu-item>
    </el-menu>
    <!-- <router-link :to="{ name: 'todo-list'}">Todo list</router-link>-->
  </el-container>
</template>
<style scoped>
#nav {
  display: flex;
  justify-content: center;
  margin: 0 auto;
  width: 100%;
  background-color: #1b1b1b;
}
#headline {
  color: #fff;
  text-align: right;
  line-height: 60px;
  width: 900px;
  padding-right: 20%;
}
.el-menu {
  background-color: #1b1b1b;
  color: #333;
  text-align: center;
  width: 100%;
  display: flex;
  justify-content: left;
}
.el-menu-item {
  display: flex;
  justify-content: center;
  background-color: #d3dce6;
  margin: auto 20px;
}
</style>
