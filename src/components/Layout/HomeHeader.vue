<template>
  <!-- 首页头部 -->
  <el-header>
    <el-row :gutter="20">
      <el-col :span="6">
        <div class="grid-content bg-purple" style="margin-top: 11px;">
          <span>dawnIceZhu's Blog</span>
        </div>
      </el-col>
      <el-col :span="18">
        <div class="grid-content bg-purple">
          <el-col :span="8" style="margin-top: 11px;">
            <el-input size="large" placeholder="请输入内容" v-model="input" clearable></el-input>
          </el-col>
          <el-col :span="15">
            <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal"
                     @select="handleSelect">
              <el-menu-item index="1">登陆</el-menu-item>
              <el-menu-item index="2" @click="handleClick">注册</el-menu-item>
              <el-menu-item index="3">管理</el-menu-item>
              <el-menu-item index="4">GITHUB</el-menu-item>
              <el-submenu index="5">
                <template slot="title">我的工作台</template>
                <el-menu-item index="5-1">选项1</el-menu-item>
                <el-menu-item index="5-2">选项2</el-menu-item>
                <el-menu-item index="5-3">选项3</el-menu-item>
                <el-submenu index="5-4">
                  <template slot="title">选项4</template>
                  <el-menu-item index="5-4-1">选项1</el-menu-item>
                  <el-menu-item index="5-4-2">选项2</el-menu-item>
                  <el-menu-item index="5-4-3">选项3</el-menu-item>
                </el-submenu>
              </el-submenu>
              <el-menu-item>
                <el-switch v-model="value" active-color="#13ce66" inactive-color="#ccc"></el-switch>
                主题切换
              </el-menu-item>
            </el-menu>
          </el-col>
        </div>
      </el-col>
    </el-row>
  </el-header>
</template>

<script>
  export default {
    name: 'HomeHeader',
    data () {
      return {
        input: '',
        activeIndex: '1',
        value: false
      }
    },
    methods: {
      handleSelect (key, keyPath) {
        console.log(key, keyPath)
      },
      handleClick () {
        this.$message({
          message: '注册功能暂不开放',
        })
      }
    }
  }
</script>

<style scoped lang="less">
  @import "src/styles/Layout/Layout";
</style>
