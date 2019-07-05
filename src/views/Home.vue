<template>
  <div class="home">
    <h1>Welcome to My Vue App</h1>
    <el-row id="home-body">
      <el-col>
        <el-card :body-style="{ padding: '0px' }">
          <img src="../assets/pizza.png" class="image">
        </el-card>
      </el-col>
      <el-col>
        <p>
          The last time you had a cheeseburger was too long ago. Try not to drool when you think about the slightly charred, medium-rare meat nestled between soft brioche, cradled in crisp iceberg lettuce and flavour amplifying condiments. Why are you still reading this- go get a cheeseburger.
          The last time you had a cheeseburger was too long ago. Try not to drool when you think about the slightly charred, medium-rare meat nestled between soft brioche, cradled in crisp iceberg lettuce and flavour amplifying condiments. Why are you still reading this- go get a cheeseburger.
        </p>
      </el-col>
    </el-row>
  </div>
</template>
<style>
#home-body {
  width: 80%;
}
p {
  padding-top: 20px;
}
</style>