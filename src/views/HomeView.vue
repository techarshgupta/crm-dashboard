<template>
  <div class="main">
    <div class="left-wrap">
      <OverView></OverView>
      <div class="charts">
        <WorkFlow></WorkFlow>
        <MarketingView></MarketingView>
      </div>
      <DocumentView></DocumentView>
    </div>
    <ProductChat></ProductChat>
  </div>
</template>

<script setup lang="ts">
import OverView from '@/components/OverView.vue'
import ProductChat from '@/components/ProductChat.vue'
import WorkFlow from '@/components/WorkFlow.vue'
import MarketingView from '@/components/MarketingView.vue'
import DocumentView from '@/components/DocumentView.vue'
</script>

<style scoped>
.main {
  display: flex;
  padding: 28px;
  gap: 28px;
  /* overflow-y: scroll; */
  /* width: 100px; */
}
.left-wrap {
  flex: 1;
}
.charts {
  display: flex;
  gap: 28px;
  padding-top: 28px;
}
@media screen and (max-width: 680px) {
  .main,
  .charts {
    flex-direction: column;
  }
}
</style>
