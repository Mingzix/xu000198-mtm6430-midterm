<template>
  <div class="contact">
    <h1>Contact</h1>
    <div class="cards">
    <el-card>
      <div slot="header" >
        <span><strong>Address</strong></span>
      </div>
      <div class="text-item">
     <p>
      1385 Woodroffe Avenue
      <br>Ottawa, Ontario K2G 1V8
      <br>613-727-4723
    </p>
  </div>
</el-card>

  <el-card>
    <div slot="header" >
      <span><strong>Hours</strong></span>
    </div>
    <div class="text-item">
     <p>
      Mon.- Thur.06:00–22:00</br>
      Fri.- Sat.06:00–22:00</br>
      Sun. 06:00–22:00</br>
      </p>
    </div>
  </el-card>
    </div>
  </div>
</template>
<style>
  

.item {
    margin-bottom: 18px;
  }
.cards {
  display: flex;
  justify-content: center;
}

  .el-card {
    width: 400px;
    margin:20px;
    padding:0px;
  }
.text-item {
  vertical-align: center;
}
</style>
