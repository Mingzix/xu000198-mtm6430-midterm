<template>
  <el-container id="nav">
    <el-aside>My Vue App</el-aside>

    <el-menu
      :default-active="activeIndex2"
      class="el-menu-demo"
      mode="horizontal"
      @select="handleSelect"
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