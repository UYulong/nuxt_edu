<template>
  <div class="_main image-ad">
    <template v-for="item in items" :key="item.src">
      <n-image width="100%" :src="item.src" class="img" />
    </template>
  </div>
</template>

<script lang="ts" setup name='ImageAd'>
import { itemsModel } from '~~/models/home';
import { NImage } from 'naive-ui'

type propsModel = {
  items: itemsModel[]
}

defineProps<propsModel>()
</script>

<style lang="scss" scoped>
.image-ad {
  margin-bottom: 20px;
}

.img {
  width: 100%;
  height: 100px;
}
</style>