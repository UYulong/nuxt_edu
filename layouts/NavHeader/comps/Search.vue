<template>
  <n-button tertiary circle @click="handleSearchClickEvent">
    <template #icon>
      <n-icon>
        <Search />
      </n-icon>
    </template>
  </n-button>
</template>

<script lang="ts" setup name='Search'>
import { NButton, NIcon } from 'naive-ui'
import { Search } from '@vicons/ionicons5'

const handleSearchClickEvent = () => {
  console.log('searching');
}
</script>

<style lang="scss" scoped>

</style>