<template>
  <div class="city top-page">
	<van-search
		v-model="searchValue"
		show-action
		shape="round"
		placeholder="请输入搜索关键词"
		@cancel = "cancelClick"
	/>
	<van-tabs v-model:active="tabActive" color="#ff9854">
		<van-tab title="国内·港澳台"></van-tab>
		<van-tab title="海外"></van-tab>
	</van-tabs>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();

// 搜索框功能实现
const searchValue =ref("")
const cancelClick = () => {
	router.back()
}

// 索引tab切换
const tabActive = ref("")

</script>
<style lang="less" scoped>
</style>