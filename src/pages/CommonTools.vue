<template>
  <el-menu
    :default-active="activeIndex2"
    class="el-menu-demo"
    mode="horizontal"
    @select="handleSelect"
    background-color="#545c64"
    text-color="#fff"
    active-text-color="#ffd04b"
  >
    <el-menu-item index="1"
      >常用工具列表
      <!-- 这里想下如何能够点击才能够实现不同导航切换 -->
      <UrlToQR />
      <IP />
    </el-menu-item>
    <el-submenu index="2">
      <template slot="title">我的工作台</template>
      <el-menu-item index="2-1">选项1</el-menu-item>
      <el-menu-item index="2-2">选项2</el-menu-item>
      <el-menu-item index="2-3">选项3</el-menu-item>
    </el-submenu>
    <el-menu-item index="3"
      ><a href="https://www.ele.me" target="_blank">订单管理</a></el-menu-item
    >
  </el-menu>
</template>

<script>
import UrlToQR from "@/pages/components/UrlToQR.vue";
import IP from "@/pages/components/IP.vue";
export default {
  name: "app",
  components: {
    UrlToQR,
    IP
  },
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
.el-menu-demo {
  width: 500px;
  height: 800px;
}
</style>
