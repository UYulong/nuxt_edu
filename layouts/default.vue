<template>
  <div class="container">
    <!-- 头部导航栏 -->
    <NavHeader />

    <!-- 中间内容区域 -->
    <main class="main">
      <slot />
    </main>

    <!-- 底部导航栏 -->
    <NavFooter />
  </div>
</template>

<script lang="ts" setup name=''>
</script>

<style lang="scss" scoped>
.container {
  min-width: 1000px;
  min-height: 100vh;
  background-color: #F5F7FA;
  display: flex;
  flex-direction: column;

  .main {
    width: 100%;
    max-width: 1200px;
    padding-left: 15px;
    padding-right: 15px;
    margin-left: auto;
    margin-right: auto;
  }
}
</style>