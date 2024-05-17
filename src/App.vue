<script setup lang="ts">
import HeaderView from '@/components/HeaderView.vue'
import SideBarView from './components/SideBarView.vue'
</script>

<template>
  <div class="">
    <SideBarView></SideBarView>
    <div class="main">
      <HeaderView></HeaderView>
      <RouterView />
    </div>
  </div>
</template>

<style scoped>
.main {
  padding-left: 260px;
}
@media screen and (max-width: 680px) {
  .main {
    padding-left: 90px;
  }
}
</style>
