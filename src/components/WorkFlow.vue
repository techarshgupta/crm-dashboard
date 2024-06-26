<template>
  <div class="card-container">
    <div class="heading">Recent Workflow</div>
    <div class="flex stats-wrap">
      <div class="stats-icon">
        <svg
          width="800px"
          height="800px"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M3 17L9 11L13 15L21 7M21 7V12M21 7H16"
            stroke="#008000"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
      </div>
      <div class="stats">17%</div>
    </div>
    <div>
      <Chart
        :size="{ width: 300, height: 200 }"
        :data="data"
        :margin="margin"
        :direction="direction"
        :axis="axis"
      >
        <template #layers>
          <Grid strokeDasharray="1,1" />
          <Area :dataKeys="['name', 'pl']" type="monotone" :areaStyle="{ fill: 'url(#grad)' }" />
          <Line
            :dataKeys="['name', 'pl']"
            type="monotone"
            :lineStyle="{
              stroke: '#9f7aea'
            }"
          />
          <Marker
            v-if="marker"
            :value="1000"
            label="Mean."
            color="green"
            strokeWidth="2"
            strokeDasharray="6 6"
          />
          <defs>
            <linearGradient id="grad" gradientTransform="rotate(90)">
              <stop offset="0%" stop-color="#be90ff" stop-opacity="1" />
              <stop offset="100%" stop-color="white" stop-opacity="0.4" />
            </linearGradient>
          </defs>
        </template>

        <template #widgets>
          <Tooltip
            borderColor="#48CAE4"
            :config="{
              pl: { color: '#9f7aea' },
              avg: { hide: true },
              inc: { hide: true }
            }"
          />
        </template>
      </Chart>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { Chart, Grid, Line, Tooltip } from 'vue3-charts'

const data = ref([
  { name: 'Jan', pl: 1000, avg: 500, inc: 300 },
  { name: 'Feb', pl: 2000, avg: 900, inc: 400 },
  { name: 'Apr', pl: 400, avg: 400, inc: 500 },
  { name: 'Mar', pl: 3100, avg: 1300, inc: 700 },
  { name: 'May', pl: 200, avg: 100, inc: 200 },
  { name: 'Jun', pl: 600, avg: 400, inc: 300 },
  { name: 'Jul', pl: 500, avg: 90, inc: 100 }
])
const direction = ref('horizontal')
const margin = ref({
  left: 0,
  top: 20,
  right: 20,
  bottom: 0
})

const axis = ref({
  primary: {
    type: 'band'
  },
  secondary: {
    // domain: ['dataMin', 'dataMax + 100'],
    type: 'linear',
    ticks: 8,
    format: () => {
      return ''
    }
  }
})
</script>

<style scoped>
.card-container {
  display: flex;
  width: 100%;
  height: 100%;
  padding: 16px;
  border-radius: 12px;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 12px;
  background-color: #fff;
}
.heading {
  font-size: 16px;
  font-weight: 700;
  padding-bottom: 16px;
}
.stats-icon {
  height: 40px;
  width: 40px;
  padding: 8px;
}
.stats-icon svg {
  width: 100%;
  height: 100%;
}
.stats {
  color: #008000;
  padding-top: 8px;
  padding-right: 16px;
}
@media screen and (max-width: 680px) {
  .card-container {
    flex-direction: column;
  }
}
</style>
