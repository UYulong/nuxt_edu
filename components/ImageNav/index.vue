<template>
  <n-grid x-gap="12" :cols="4">
    <n-gi v-for="item in items" :key="item.src">
      <n-card @click="$commonOpen(item)" class="card">
        <template #cover>
          <img :src="item.src" class="img">
        </template>
        <div class="title">{{item.name}}</div>
      </n-card>
    </n-gi>
  </n-grid>
</template>

<script lang="ts" setup name='ImageNav'>
import { NGrid, NGi, NCard } from 'naive-ui'
import { itemsModel } from '~~/models/home';

type propsModel = {
  items: itemsModel[]
}

defineProps<propsModel>()
</script>

<style lang="scss" scoped>
.card {
  margin-bottom: 20px;
}
.img {
  cursor: pointer;
}
.title {
  text-align: center;
  padding-top: 15px;
}
</style>