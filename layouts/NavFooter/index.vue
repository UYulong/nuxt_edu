<template>
  <div class="footer _main">
    <!-- 链接 -->
    <ul class="link">
      <li v-for="n in 5">
        <a href="#">视频课程</a>
      </li>
    </ul>


    <!-- 版权信息 -->
    <div class="copy">
      <small>
        Copyright © 2022 dishait.cn 粤ICP备2020100536号
      </small>
    </div>
  </div>
</template>

<script lang="ts" setup name='NavFooter'>
</script>

<style lang="scss" scoped>
.footer {
  height: 120px;

  .link {
    display: flex;
    justify-content: center;
    padding: 15px 0;

    li {
      margin-right: 50px;

      a {
        color: rgb(164, 159, 159);

      }
    }
  }

  .copy {
    border-top: 1px solid rgb(71, 71, 71);
    text-align: center;
    padding: 5px 0;
    color: rgb(164, 159, 159);
  }
}
</style>