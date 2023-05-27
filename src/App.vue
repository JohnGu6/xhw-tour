<template>
  <div class="app">
    <RouterView></RouterView>
    <!-- <Tabbar v-if="!route.meta.hideTabbar"></Tabbar> -->
    <Tabbar />
  </div>
</template>

<script setup>
import Tabbar from './components/TabBar/tabbar.vue';
import { useRoute } from "vue-router";

const route = useRoute()


</script>
<style scoped>
</style>