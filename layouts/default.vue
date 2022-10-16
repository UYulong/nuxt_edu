<template>
  <n-layout class="container">
    <n-layout-header>
      <!-- 头部导航栏 -->
      <NavHeader />
    </n-layout-header>

    <!-- 中间内容区域 -->
    <n-layout-content content-style="padding: 0;" class="_main">
      <slot />
    </n-layout-content>

    <n-layout-footer>
      <!-- 底部导航栏 -->
      <NavFooter />
    </n-layout-footer>
  </n-layout>
</template>

<script lang="ts" setup name=''>
import NavHeader from './NavHeader/index.vue'
import { NLayout, NLayoutHeader, NLayoutContent, NLayoutFooter } from 'naive-ui'
</script>

<style lang="scss" scoped>
.container {
  min-width: 1000px;
  min-height: 100vh;
  background-color: #F5F7FA;
  display: flex;
  flex-direction: column;
}
</style>