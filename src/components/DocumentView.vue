<template>
  <div class="document-wrap">
    <div class="header">
      <div>
        <div class="title">Document</div>
        <div class="sub">Document tracking information</div>
      </div>
    </div>
    <div>
      <table>
        <thead>
          <th class="heading">Name</th>
          <th class="heading">File</th>
          <th class="heading">Category</th>
          <th class="heading">Author</th>
          <th class="heading">Status</th>
        </thead>
        <tbody>
          <tr v-for="(item, idx) in data" :key="idx">
            <td>{{ item.name }}</td>
            <td>{{ item.file }}</td>
            <td>{{ item.category }}</td>
            <td>{{ item.Author }}</td>
            <td>
              <div v-if="item.status === 'Send'" class="send">{{ item.status }}</div>
              <div v-else class="pending">{{ item.status }}</div>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const data = ref([
  {
    name: 'Annual report',
    file: 'PDF',
    category: 'Property',
    Author: 'Diana Matthews',
    status: 'Send'
  },
  {
    name: 'Business plan',
    file: 'WORD',
    category: 'Cryptocurrency',
    Author: 'Pillip james',
    status: 'Send'
  },
  {
    name: 'Marketing tool',
    file: 'PDF',
    category: 'Cantent creator',
    Author: 'Amanda ross',
    status: 'Pending'
  }
])
</script>

<style scoped>
.document-wrap {
  display: flex;
  flex-direction: column;
  width: 100%;
  padding: 16px;
  border-radius: 12px;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 12px;
  background-color: #fff;
  margin-top: 28px;
  overflow-x: scroll;
}
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.title {
  font-size: 18px;
  font-weight: 700;
}
.sub {
  font-size: 14px;
  padding-top: 6px;
  color: rgb(130, 126, 126);
}
.heading {
  font-size: 14px;
  font-weight: 700;
}
table {
  width: 100%;
  padding-top: 16px;
}
td {
  padding: 8px 12px;
  font-weight: 500;
  font-size: 14px;
}
th {
  padding: 8px 12px;
  text-align: left;
  font-size: 18px;
}
.pending {
  padding: 8px 12px;
  background-color: #f9c4ba;
  color: #b8533e;
  font-weight: bold;
  width: 100px;
  border-radius: 4px;
  text-align: center;
}
.send {
  padding: 8px 12px;
  color: green;
  text-align: center;
  font-weight: bold;
  width: 100px;
  border-radius: 4px;
  background-color: rgb(187, 244, 187);
}
</style>
