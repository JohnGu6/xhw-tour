<template>
  <div class="home-search">
	<div class="location">
      <div class="city" @click="cityClick">
		北京
	  </div>
      <div class="position" @click="positionClick">
        <span class="text">我的位置</span>
        <img src="@/assets/img/home/icon_location.png" alt="">
      </div>
    </div>
  </div>
</template>

<script setup>
import { useRouter } from "vue-router";

const router = useRouter()

//城市信息
const cityClick = () => {
	router.push("/city")
}

//获取位置信息
const positionClick = () => {
	navigator.geolocation.getCurrentPosition(res => {
		console.log("pass",res)
	}, err => {
		console.log("fail",err)
	},{
  		enableHighAccuracy: true,
  		timeout: 5000,
  		maximumAge: 0
	})
}
</script>
<style lang="less" scoped>
.location {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 44px;
  padding: 0 20px;
  .city {
    flex: 1;
    color: #333;
    font-size: 15px;
  }
  .position {
    width: 74px;
    display: flex;
    align-items: center;
    .text {
      font-size: 12px;
      position: relative;
      top: 2px;
      color: #666;
    }
    img {
      margin-left: 5px;
      width: 18px;
      height: 18px;
    }
  }
}
</style>