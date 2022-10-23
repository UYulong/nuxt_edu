<template>
  <p class="price">
    <span class="now">¥{{price}}</span>
    <span class="before">¥{{t_price}}</span>
  </p>
</template>

<script lang="ts" setup name='Price'>
type propsModel = {
  price: string
  t_price: string
}

defineProps<propsModel>()
</script>

<style lang="scss" scoped>
.price {
  .now {
    font-size: 18px;
    color: red;
    font-weight: 600;
  }

  .before {
    font-size: 12px;
    color: gray;
    margin-left: 8px;
    text-decoration-line: line-through;
  }

}
</style>