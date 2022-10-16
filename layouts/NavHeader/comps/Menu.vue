<template>
  <n-menu v-model:value="activeKey" mode="horizontal" :options="menuOptions" default-value="home" />
</template>

<script lang="ts" setup name='Menu'>
import { MenuOption, NMenu } from 'naive-ui';
import { RouterLink } from 'vue-router';

// 菜单激活项
const activeKey = ref<string | null>(null)

// 监听 地址，菜单高亮显示
const route = useRoute()
watchEffect(() => {
  if (route.path) {
    activeKey.value = route.path
  }
})

// menu 菜单数据项
const menuOptions: MenuOption[] = [
  {
    label: () =>
      h(
        RouterLink,
        {
          to: {
            path: '/',
          }
        },
        { default: () => '首页' }
      ),
    key: '/',
  },
  {
    label: () =>
      h(
        RouterLink,
        {
          to: {
            path: '/exam',
          }
        },
        { default: () => '考试' }
      ),
    key: '/exam',
  },
  {
    label: () =>
      h(
        RouterLink,
        {
          to: {
            path: '/group',
          }
        },
        { default: () => '拼团' }
      ),
    key: '/group',
  },
  {
    label: () =>
      h(
        RouterLink,
        {
          to: {
            path: '/seckill',
          }
        },
        { default: () => '秒杀' }
      ),
    key: '/seckill',
  },
  {
    label: () =>
      h(
        RouterLink,
        {
          to: {
            path: '/live',
          }
        },
        { default: () => '直播' }
      ),
    key: '/live',
  },
  {
    label: () =>
      h(
        RouterLink,
        {
          to: {
            path: '/column',
          }
        },
        { default: () => '专栏' }
      ),
    key: '/column',
  },
  {
    label: () =>
      h(
        RouterLink,
        {
          to: {
            path: '/book',
          }
        },
        { default: () => '电子书' }
      ),
    key: '/book',
  },
  {
    label: () =>
      h(
        RouterLink,
        {
          to: {
            path: '/community',
          }
        },
        { default: () => '社区' }
      ),
    key: '/community',
  },
  {
    label: () =>
      h(
        RouterLink,
        {
          to: {
            path: '/course',
          }
        },
        { default: () => '课程' }
      ),
    key: '/course',
  },
]
</script>

<style lang="scss" scoped>

</style>