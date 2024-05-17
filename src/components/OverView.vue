<template>
  <div class="overview-wrap">
    <div class="card-container" v-for="(item, idx) in overview" :key="idx">
      <div class="flex item-center space-between">
        <div class="title">{{ item.title }}</div>
        <div class="icon-wrap">
          <svg
            v-if="item.title === 'Document'"
            width="800px"
            height="800px"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M15.6111 1.5837C17.2678 1.34703 18.75 2.63255 18.75 4.30606V5.68256C19.9395 6.31131 20.75 7.56102 20.75 9.00004V19C20.75 21.0711 19.0711 22.75 17 22.75H7C4.92893 22.75 3.25 21.0711 3.25 19V5.00004C3.25 4.99074 3.25017 4.98148 3.2505 4.97227C3.25017 4.95788 3.25 4.94344 3.25 4.92897C3.25 4.02272 3.91638 3.25437 4.81353 3.12621L15.6111 1.5837ZM4.75 6.75004V19C4.75 20.2427 5.75736 21.25 7 21.25H17C18.2426 21.25 19.25 20.2427 19.25 19V9.00004C19.25 7.7574 18.2426 6.75004 17 6.75004H4.75ZM5.07107 5.25004H17.25V4.30606C17.25 3.54537 16.5763 2.96104 15.8232 3.06862L5.02566 4.61113C4.86749 4.63373 4.75 4.76919 4.75 4.92897C4.75 5.10629 4.89375 5.25004 5.07107 5.25004ZM7.25 12C7.25 11.5858 7.58579 11.25 8 11.25H16C16.4142 11.25 16.75 11.5858 16.75 12C16.75 12.4143 16.4142 12.75 16 12.75H8C7.58579 12.75 7.25 12.4143 7.25 12ZM7.25 15.5C7.25 15.0858 7.58579 14.75 8 14.75H13.5C13.9142 14.75 14.25 15.0858 14.25 15.5C14.25 15.9143 13.9142 16.25 13.5 16.25H8C7.58579 16.25 7.25 15.9143 7.25 15.5Z"
              fill="#1C274D"
            />
          </svg>
          <svg
            v-if="item.title === 'Contact'"
            xmlns="http://www.w3.org/2000/svg"
            width="800px"
            height="800px"
            viewBox="0 0 24 24"
            id="Layer_1"
            data-name="Layer 1"
          >
            <rect class="cls-1" x="5.32" y="1.5" width="13.36" height="21" rx="1.91" />
            <line class="cls-1" x1="5.32" y1="18.68" x2="18.68" y2="18.68" />
            <circle class="cls-1" cx="12" cy="8.18" r="1.91" />
            <path
              class="cls-1"
              d="M12,10.09h0A2.86,2.86,0,0,1,14.86,13v1a0,0,0,0,1,0,0H9.14a0,0,0,0,1,0,0V13A2.86,2.86,0,0,1,12,10.09Z"
            />
          </svg>
          <svg
            v-if="item.title === 'Email'"
            xmlns="http://www.w3.org/2000/svg"
            width="800px"
            height="800px"
            viewBox="0 0 24 24"
            fill="none"
          >
            <path
              d="M4 7L10.94 11.3375C11.5885 11.7428 12.4115 11.7428 13.06 11.3375L20 7M5 18H19C20.1046 18 21 17.1046 21 16V8C21 6.89543 20.1046 6 19 6H5C3.89543 6 3 6.89543 3 8V16C3 17.1046 3.89543 18 5 18Z"
              stroke="#000000"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </div>
      </div>
      <div class="stats-title">{{ item.count }}</div>
      <div class="flex item-center stats-wrap">
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
        <div class="stats">{{ item.percentage }}</div>
        <div class="duration">{{ item.duration }}</div>
      </div>
    </div>
    <!-- <ProductChat></ProductChat> -->
  </div>
</template>

<script setup>
// import ProductChat from './ProductChat.vue'
import { ref } from 'vue'

const overview = ref([
  {
    title: 'Document',
    count: '146.000',
    percentage: '17%',
    duration: 'Since last week'
  },
  {
    title: 'Contact',
    count: '1400',
    percentage: '17%',
    duration: 'Since last week'
  },
  {
    title: 'Email',
    count: '150.700',
    percentage: '17%',
    duration: 'Since last week'
  }
])
</script>

<style scoped>
.overview-wrap {
  display: flex;
  gap: 24px;
}
@media screen and (max-width: 680px) {
  .overview-wrap {
    flex-direction: column;
  }
}
.card-container {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 200px;
  padding: 16px;
  border-radius: 12px;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 12px;
  background-color: #fff;
}
.title {
  font-size: 16px;
  font-weight: 500;
}
.icon-wrap {
  height: 40px;
  width: 40px;
  padding: 8px;
  border-radius: 50%;
  background-color: var(--theme-bg-primary);
}
.icon-wrap svg {
  width: 100%;
  height: 100%;
}
.stats-title {
  font-size: 32px;
  margin-top: 32px;
  font-weight: 700;
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
.stats-wrap {
  align-items: flex-end;
  flex: 1;
}
.stats {
  font-size: 14px;
  color: #008000;
  font-weight: 500;
  padding-bottom: 12px;
}
.duration {
  font-size: 14px;
  padding-left: 12px;
  padding-bottom: 12px;
  color: rgb(130, 126, 126);
}
.cls-1 {
  fill: none;
  stroke: #1c274d;
  stroke-miterlimit: 10;
  stroke-width: 1.91px;
}
</style>
