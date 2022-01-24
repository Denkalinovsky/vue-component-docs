<template>
  <el-container
    class="layout-container-demo"
    style="height: 100%; border: 1px solid #eee"
  >
    <el-aside width="200px" style="background-color: rgb(238, 241, 246)">
      <el-scrollbar>
        <el-menu :default-openeds="[]">
          <el-menu index="1">
            <el-icon><message /></el-icon><router-link to="/">Home</router-link>
          </el-menu>
          <el-menu index="2">
            <el-icon><setting /></el-icon
            ><router-link to="/budget">Budget</router-link>
          </el-menu>
        </el-menu>
      </el-scrollbar>
    </el-aside>

    <router-view />
  </el-container>
</template>

<script>
export default {
  name: "LeftMenu",
};
</script>

<style scoped></style>
