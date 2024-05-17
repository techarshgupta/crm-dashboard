<template>
  <div class="prod-card-container">
    <div class="heading">Popular Products</div>
    <div class="product-card" v-for="(prod, idx) in products" :key="idx">
      <div class="icon"></div>
      <div class="body-wrap">
        <div class="title">{{ prod.title }}</div>
        <div class="sub">{{ prod.price }}</div>
      </div>
    </div>
    <div class="heading">Chat</div>
    <div class="product-card" v-for="(prod, idx) in chats" :key="idx">
      <div class="icon"></div>
      <div class="body-wrap">
        <div class="title">{{ prod.name }}</div>
        <div class="sub">{{ prod.msg }}</div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const products = ref([
  {
    title: 'Gadget Convertor',
    price: '$250'
  },
  {
    title: 'Lens Camera',
    price: '$50'
  },
  {
    title: 'Airpods',
    price: '$99'
  },
  {
    title: 'Mackbook',
    price: '$999'
  }
])
const chats = ref([
  {
    name: 'Debra Young',
    msg: "How's my product?"
  },
  {
    name: 'Dorothy Collins',
    msg: 'How was the meeting'
  },
  {
    name: 'Chris Jordan',
    msg: 'How employee performance'
  },
  {
    name: 'Denise Murphy',
    msg: 'How was the meeting'
  }
])
</script>

<style scoped>
.prod-card-container {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 100%;
  padding: 16px;
  border-radius: 12px;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 12px;
  background-color: #fff;
  max-width: 300px;
}
.heading {
  font-size: 16px;
  font-weight: 700;
  padding-bottom: 16px;
}
.product-card {
  display: flex;
  align-items: center;
  margin: 16px 0;
}
.product-card .icon {
  height: 50px;
  width: 50px;
  background-color: var(--theme-dark);
  border-radius: 50%;
}
.product-card .body-wrap {
  padding-left: 16px;
}
.body-wrap .title {
  font-size: 16px;
  font-weight: 500;
}
.body-wrap .sub {
  font-size: 12px;
  padding-top: 6px;
  color: rgb(130, 126, 126);
}
@media screen and (max-width: 680px) {
  .prod-card-container {
    max-width: 100%;
  }
}
</style>
