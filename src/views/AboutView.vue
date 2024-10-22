<script setup lang="ts">
import { useRoute } from 'vue-router'
import { computed } from 'vue'
import { type DataType, datas } from '@/libs/constants'

const route = useRoute()

const users: DataType[] = computed(() => {
  return datas.filter(item =>
    Object.entries(route.query).every(([key, value]) => {
      if (key === 'completed') {
        const checked = value === '1' ? true : value === '0' ? false : undefined
        return item[key] === checked
      }

      if (key === 'title') {
        return item[key].includes(value)
      }

      return item[key as DataType] === value
    }),
  )
})
</script>

<template>
  <div>
    <h1>This is an about page {{ $route.fullPath }}</h1>
    <h1>{{ users.length }}</h1>
    <ul>
      <li v-for="data of users" :key="data.id">
        {{ data }}
      </li>
    </ul>
  </div>
</template>
