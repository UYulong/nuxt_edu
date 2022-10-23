<template>
  <div>
    <n-grid x-gap="12" :cols="4">
      <n-gi v-for="item in data" :key="item.id">
        <n-card @click="$commonOpen(item)" class="card" footer-style="padding: 0;">
          <template #cover>
            <img :src="item.cover" class="img">
          </template>
          <div class="text">
            <p class="title">{{item.title}}</p>
            <Price :price="item.price" :t_price="item.t_price" />
          </div>

          <!-- 倒计时 -->
          <template #footer v-if="item.group_id">
            <div class="count-down">
              <p>拼团中</p>
              <CountDown :date="item.end_time" />
            </div>
          </template>
        </n-card>
      </n-gi>
    </n-grid>
  </div>
</template>

<script lang="ts" setup name='ListCard'>
import { NGrid, NGi, NCard } from 'naive-ui'
import { groupItemsModel } from '~~/models/home';

type propsModel = {
  data: groupItemsModel[]
}

defineProps<propsModel>()
</script>

<style lang="scss" scoped>
.card {
  margin-bottom: 20px;
}

.img {
  cursor: pointer;
  height: 150px;
}

.text {
  padding-top: 15px;
}

.count-down {
  color: #fff;
  padding: 12px 15px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom-left-radius: 3px;
  border-bottom-right-radius: 3px;
  background-color: #e9a23b;

  .time {
    font-size: 12px;

    small {
      color: #e9a23b;
      background-color: #fff;
      padding: 3px 2px;
      border-radius: 3px;
    }
  }
}
</style>