<template>
  <div class="tabbar">
	<van-tabbar v-model="currentIndex" active-color="#ff9854">
		<template v-for="(item, index) in tabbarData">
			<van-tabbar-item :to="item.path">
			<span>{{item.text}}</span>
    		<template #icon>
				<img v-if ="currentIndex !== index" :src="getAssetURL(item.image)" alt="">
			  	<img v-else :src="getAssetURL(item.imageActive)" alt="">	
    		</template>
		</van-tabbar-item>
	  </template>
</van-tabbar>

  </div>
</template>

<script setup>

import tabbarData from "@/assets/data/tabbar.js"
import { getAssetURL } from "@/utils/get-asset-imgurl";
import { ref } from "vue";

const currentIndex = ref(0)

</script>
<style lang="less" scoped>

.tabbar {
	--van-tabbar-item-icon-size:30px !important;
	img{
		height: 28px;
	}
}
</style>