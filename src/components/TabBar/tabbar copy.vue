<template>
	<div class="tabbar">
	  <template v-for="(item, index) in tabbarData">
		  <div class="tabbar-item" 
			  :class="{ active:currentIndex === index }"
			  @click="itemClick(index, item)"
			  >
			  <img v-if ="currentIndex !== index" :src="getAssetURL(item.image)" alt="">
			  <img v-else :src="getAssetURL(item.imageActive)" alt="">
			  <span class="text">{{ item.text}}</span>
		  </div>
	  </template>
	</div>
  </template>
  
  <script setup>
  
  import tabbarData from "@/assets/data/tabbar.js"
  import { getAssetURL } from "@/utils/get-asset-imgurl";
  import { ref } from "vue";
  import { useRouter } from "vue-router";
  
  const currentIndex = ref(0)
  const router = useRouter()
  const itemClick = (index, item) => {
	  currentIndex.value = index
	  router.push(item.path)
  }
  
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
  
		  &.active {
			  color: var(--primary-color);
		  }
		  
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