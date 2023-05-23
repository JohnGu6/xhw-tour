<template>
  <div class="tabbar">
	<div class="tabbar-item">
		<img src="@/assets/img/tabbar/tab_home.png" alt="">
		<span class="text">首页</span>
	</div>
	<div class="tabbar-item">
		<img src="@/assets/img/tabbar/tab_collect.png" alt="">
		<span class="text">收藏</span>
	</div>
	<div class="tabbar-item">
		<img src="@/assets/img/tabbar/tab_order.png" alt="">
		<span class="text">订单</span>
	</div>
	<div class="tabbar-item">
		<img src="@/assets/img/tabbar/tab_message.png" alt="">
		<span class="text">消息</span>
	</div>
  </div>
</template>

<script setup>

</script>
<style lang="less" scoped>

.tabbar {
	display: flex;
	height: 50px;
	position: fixed;
	bottom: 0;
	left: 0;
	right: 0;
	border-top: 1px solid #f3f3f3;

	.tabbar-item {
		flex: 1;
		display: flex;
		flex-direction: column; 
		justify-content: center;
		align-items: center;
		
		.text {
			font-size: 12px;
			margin-top: 2px;
		}
		img {
			width: 32px;
		}
	}
}
</style>