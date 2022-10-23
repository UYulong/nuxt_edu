<template>
  <div class="home">
    <template v-if="pending">
      加载中....
    </template>

    <template v-if="error">
      错误提示：{{error?.data?.data}}
    </template>

    <template v-else>
      <Banner :items="listAll.bannerList" />
      <ImageNav :items="listAll.imgNavList" />
      <ImageAd :items="listAll.imgAdList" />
      <List :items="listGroup" title="拼团"/>
      <List :items="newList" />
      <List :items="recommendList" />
    </template>
  </div>
</template>

<script lang="ts" setup name='Home'>
const listAll = ref({
  bannerList: [], // banner
  imgNavList: [], // 卡片导航数据
  imgAdList: [], // 广告
})

// 最新列表
const newList = ref({
  checked: null,
  data: [],
  listType: null,
  title: null,
  type: null,
  more: null,
  showMore: null
})
// 推荐列表
const recommendList = ref({
  checked: null,
  data: [],
  listType: null,
  title: null,
  type: null,
  more: null,
  showMore: null
})

// 获取首页数据
const { data, pending, error } = await useFetch('/index', {
  key: "IndexData",
  baseURL: 'http://demonuxtapi.dishait.cn/pc',
  headers: {
    appid: 'bd9d01ecc75dbbaaefce'
  },
  transform: (res: any) => {
    return res.data
  },
  initialCache: false,
  lazy: true
})
watchEffect(() => {
  if (Object.keys(data).length > 0) {
    data.value.forEach(item => {
      if (item.type === 'swiper') {
        listAll.value.bannerList = item.data
      } else if (item.type === 'icons') {
        listAll.value.imgNavList = item.data
      } else if (item.type === 'imageAd') {
        listAll.value.imgAdList = item.data
      } else if (item.type === 'list' && item.title === '最新列表') {
        newList.value = Object.assign(newList.value, item)
      } else if (item.type === 'list' && item.title === '推荐列表') {
        recommendList.value = Object.assign(recommendList.value, item)
      }
    })
  }
})

// 拼团数据
const listGroup = ref({
  count: null,
  data: []
})
const { data: groupData, } = await useFetch('/group/list?page=1&usable=1&limit=8', {
  key: "groupData",
  baseURL: 'http://demonuxtapi.dishait.cn/pc',
  headers: {
    appid: 'bd9d01ecc75dbbaaefce'
  },
  transform: (res: any) => {
    return res.data
  },
  initialCache: false,
})

watchEffect(() => {
  if (Object.keys(groupData).length > 0) {
    listGroup.value.count = groupData.value.count
    listGroup.value.data = groupData.value.rows
  }
})
console.log(groupData.value);

// 如果服务端报错
if (process.server && error.value) {
  throwError(error.value?.data?.data)
}
</script>

<style lang="scss" scoped>

</style>