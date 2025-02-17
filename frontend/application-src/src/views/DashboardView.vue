<script setup lang="ts">
import { ref } from 'vue'
import { RouterView } from 'vue-router'
import type { CSSProperties } from 'vue'

const tabs = ref(['Books', 'Saved', 'Profile'])

const activeTab = ref(tabs.value[0])

const footerStyle: CSSProperties = {
  border: '1px solid black',
  position: 'fixed',
  bottom: 0,
  width: '100%',
  padding: '0',
}
</script>

<template>
  <a-layout>
    <a-layout-header>Header</a-layout-header>

    <a-layout-content>
      <RouterView />
    </a-layout-content>

    <a-layout-footer :style="footerStyle">
      <a-segmented block size="large" v-model:value="activeTab" :options="tabs" />
    </a-layout-footer>
  </a-layout>
</template>

<style scoped></style>
