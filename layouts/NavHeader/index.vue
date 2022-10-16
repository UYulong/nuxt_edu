<template>
  <div class="header-container">
    <div class="_main nav-header">
      <!-- 左侧 logo 和 菜单 -->
      <div class="nav-left">
        <Logo />
        <Menu />
      </div>

      <!-- 右侧 搜索 和 头像 -->
      <div class="nav-right">
        <Search />
        <Avatar />
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup name='NavHeader'>
import Logo from './comps/Logo.vue'
import Menu from './comps/Menu.vue'
import Search from './comps/Search.vue'
import Avatar from './comps/Avatar.vue'
</script>

<style lang="scss" scoped>
.header-container {
  height: 60px;
  background-color: #fff;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
  margin-bottom: 10px;

  .nav-header {
    height: 100%;
    display: flex;
    align-items: center;

    .nav-left {
      display: flex;
      align-items: center;
    }

    .nav-right {
      display: flex;
      align-items: center;
      margin-left: auto;
    }
  }
}
</style>