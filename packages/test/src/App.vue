<template>
  <div>
    <Tab v-model="current" :items="items" />
    <div>
      当前选中的是：{{  current  }}
    </div>
  </div>
</template>
<script setup lang="ts">
import { ref } from 'vue'
import { Tab } from '@newbee/ui'
const items = [
  { label: '天气', value: 1 },
  { label: '新闻', value: 2 },
  { label: '娱乐', value: 3 },
]
const current = ref(1)
</script>

<style scoped>
</style>
