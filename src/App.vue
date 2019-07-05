<template>
  <div id="app">
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

    <router-view/>
  </div>
</template>
<!----
<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app",
  components: {
    HelloWorld
  }
};
</script>
--->
<script>
export default {
  data() {
    return {
      activeIndex: "1",
      activeIndex2: "1"
    };
  },
  methods: {
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    }
  }
};
</script>
<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0 auto;
  margin-top: 0px;
}
.nav {
  display: flex;
  justify-content: center;
  margin: 0 auto;
  width: 100%;
}
.el-aside {
  background-color: #1b1b1b;
  color: #fff;
  text-align: right;
  line-height: 60px;
  width: 100%;
  padding-right: 50px;
}
.el-menu {
  background-color: #1b1b1b;
  color: #333;
  text-align: center;
  line-height: 60px;
  width: 100%;
}
.el-menu-item {
  display: flex;
  justify-content: center;
  background-color: #d3dce6;
}
</style>
