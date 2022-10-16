<template>
  <div class="avatar">
    <n-dropdown trigger="hover" :options="options" @select="handleSelect">
      <n-avatar round size="medium" src="https://pic.imgdb.cn/item/6315b85b16f2c2beb1666188.png" />
    </n-dropdown>
  </div>
</template>

<script lang="ts" setup name='Avatar'>
import { NAvatar, NDropdown } from 'naive-ui'

const options = [
  {
    label: '用户中心',
    key: 'center',
  },
  {
    label: '退出',
    key: "logout"
  },
]

const handleSelect = (key: string | number) => {
  console.log(String(key));
}
</script>

<style lang="scss" scoped>
.avatar {
  margin-left: 20px;
}
</style>