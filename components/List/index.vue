<template>
  <div class="list-container">
    <div class="title">
      <h3>{{title ? title :items.title}}</h3>
      <n-button text tag="a" href="https://anyway.fm/news.php" target="_blank" type="primary">
        查看更多
      </n-button>
    </div>

    <ListCard :data="items.data" />
  </div>
</template>

<script lang="ts" setup name='List'>
import { NButton } from 'naive-ui'
import { groupItemsModel } from '~~/models/home';

type itemsModel = {
  checked?: boolean
  data: groupItemsModel[]
  listType?: string
  title?: string
  type?: string
  more?: boolean
  showMore?: boolean
}
type propsModel = {
  items: itemsModel
  title?: string
}
defineProps<propsModel>()
</script>

<style lang="scss" scoped>
.list-container {
  .title {
    display: flex;
    justify-content: space-between;
  }
}
</style>