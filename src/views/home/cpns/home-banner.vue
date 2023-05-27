<template>
  <div class="banner">
    <van-swipe :autoplay="2000" lazy-render>
      <van-swipe-item v-for="(item) in bannerData">
          <img :src="getAssetURL(item.image)" alt="" />
      </van-swipe-item>
    </van-swipe>
  </div>
</template>

<script setup>
import bannerData from "@/assets/data/banner"
import { getAssetURL } from "@/utils/get-asset-imgurl";
</script>
<style lang="less" scoped>
.banner {
  img {
    width: 100%;
  }
}
</style>