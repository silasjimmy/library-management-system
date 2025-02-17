<script setup lang="ts">
import { ref } from 'vue'
import { RouterView } from 'vue-router'

const tabs = ref(['Books', 'Saved', 'Profile'])

const activeTab = ref(tabs.value[0])
</script>

<template>
  <a-layout>
    <a-layout-header>Header</a-layout-header>

    <a-layout-content>
      <RouterView />
    </a-layout-content>

    <a-layout-footer>
      <a-segmented block v-model:value="activeTab" :options="tabs" />
    </a-layout-footer>
  </a-layout>
</template>

<style scoped></style>
