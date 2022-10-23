<template>
  <p class="time">
    倒计时
    <small>{{date.group_id}}</small> 天
    <small>{{date.group_id}}</small> :
    <small>{{date.group_id}}</small> :
    <small>{{date.group_id}}</small>
  </p>
</template>

<script lang="ts" setup name='CountDown'>
const props = defineProps<{
  date: string
}>()

// const time = useCountDown(props.date)

// function useCountDown(date) {
//   if (typeof date === 'string') {
//     console.log(date);
//     const 

//   }

// }
</script>

<style lang="scss" scoped>

</style>