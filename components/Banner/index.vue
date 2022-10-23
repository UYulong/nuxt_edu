<template>
  <div class="carousel-container">
    <n-carousel show-arrow>
      <template v-for="item in items" :key="item.src">
        <img class="carousel-img" :src="item.src" @click="$commonOpen(item)">
      </template>
    </n-carousel>
  </div>
</template>

<script lang="ts" setup name='Banner'>
import { NCarousel } from 'naive-ui'
import { itemsModel } from '~~/models/home';

type propsModel = {
  items: itemsModel[]
}
defineProps<propsModel>()
</script>

<style lang="scss" scoped>
.carousel-container {
  margin-bottom: 20px;

  .carousel-img {
    border-radius: 5px;
    cursor: pointer;
  }
}
</style>