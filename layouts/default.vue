<template>
  <div class="container">
    <n-layout-header class="header">
      <!-- 头部导航栏 -->
      <NavHeader />
    </n-layout-header>

    <!-- 中间内容区域 -->
    <n-layout-content content-style="padding: 0;" class="_main main">
      <slot />
    </n-layout-content>

    <n-layout-footer class="footer">
      <!-- 底部导航栏 -->
      <NavFooter />
    </n-layout-footer>
  </div>
</template>

<script lang="ts" setup name=''>
import NavHeader from './NavHeader/index.vue'
import NavFooter from './NavFooter/index.vue'
import { NLayoutHeader, NLayoutContent, NLayoutFooter } from 'naive-ui'
</script>

<style lang="scss" scoped>
.container {
  min-width: 1000px;
  min-height: 100vh;
  background-color: #F5F7FA;
  display: flex;
  flex-direction: column;

  .header {
    height: 60px;
  }

  .main {
    margin: 10px auto;
    background-color: #F5F7FA;
  }

  .footer {
    background-color: #232221;
    display: flex;
    flex-direction: column;
  }
}
</style>