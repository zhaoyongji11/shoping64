<template>
  <el-container class="container">
    <el-header>
      <el-row>
        <el-col :span="4">
          <img src="@/assets/logo.png" alt="图片加载失败">
        </el-col>
        <el-col :span="19" class="middle">
         <h2>电商管理后台系统</h2>
        </el-col>
        <el-col :span="1">
        <a href="#" class="logout">退出</a>
        </el-col>
      </el-row>
    </el-header>
    <el-container>
      <el-aside
        width="200px"
        class="aside"
      >Aside</el-aside>
      <el-main class="main">Main</el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {};
</script>

<style>
.container {
  height: 100%;
  background-color: #B3c0D1;
}
.aside {
  background-color: yellow;
}
.main {
  background-color: green;
}
.middle{
    line-height: 30px;
    text-align: center;
    color: #fff;
}
.logout{
    line-height: 60px;
    text-decoration: none;
}
</style>
