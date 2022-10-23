<template>
  <div class="error-page">
    <n-result status="418" title="418 我是个杯具" :description="error.message">
      <template #footer>
        <n-button @click="handleError">接受真相就是这么简单</n-button>
      </template>
    </n-result>
  </div>

</template>

<script lang="ts" setup name="ErrorPage">
import { NResult, NButton } from 'naive-ui'

defineProps({
  error: Object
})

const handleError = () => clearError({ redirect: '/' })
</script>

<style lang="scss" scoped>
.error-page {
  padding-top: 10%;
}
</style>
