<template>
  <div class="about">
    <h1>About the Vue App</h1>
    <el-row>
      <el-col>
        <el-card id="about-card" :body-style="{ padding: '0px' }">
          <img src="../assets/pizza.png" class="image">
        </el-card>
      </el-col>
      <el-col id="about-card">
        <p>
          The last time you had a cheeseburger was too long ago. Try not to drool when you think about the slightly charred, medium-rare meat nestled between soft brioche, cradled in crisp iceberg lettuce and flavour amplifying condiments. Why are you still reading this- go get a cheeseburger.
          The last time you had a cheeseburger was too long ago. Try not to drool when you think about the slightly charred, medium-rare meat nestled between soft brioche, cradled in crisp iceberg lettuce and flavour amplifying condiments. Why are you still reading this- go get a cheeseburger.
        </p>
      </el-col>
    </el-row>
    <el-row>
      <el-col>
        <p>
          The last time you had a cheeseburger was too long ago. Try not to drool when you think about the slightly charred, medium-rare meat nestled between soft brioche, cradled in crisp iceberg lettuce and flavour amplifying condiments. Why are you still reading this- go get a cheeseburger.
          The last time you had a cheeseburger was too long ago. Try not to drool when you think about the slightly charred, medium-rare meat nestled between soft brioche, cradled in crisp iceberg lettuce and flavour amplifying condiments. Why are you still reading this- go get a cheeseburger.
        </p>
      </el-col>
      <el-col>
        <el-card id="about-card" :body-style="{ padding: '0px' }">
          <img src="../assets/pizza.png" class="image">
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>
<style>
.time {
  color: #999;
}
.el-col {
  width: 50%;
  display: flex;
  justify-content: center;
}
.el-row {
  padding-top: 20px;
  width: 80%;
  margin: 0 auto;
  display: flex;
  justify-content: center;
}

#about-card {
  width: 100%;
  height: 80%;
}

.image {
  width: 100%;
  display: block;
}

.clearfix:before,
.clearfix:after {
  display: table;
  content: "";
}
.clearfix:after {
  clear: both;
}
#about-text {
  padding-right: 10px;
}
</style>
