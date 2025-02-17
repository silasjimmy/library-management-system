<script setup lang="ts">
import { ref } from 'vue'

let drawerOpen = ref(false)

function showDrawer() {
  drawerOpen.value = true
}

function closeDrawer() {
  drawerOpen.value = false
}
</script>

<template>
  <div class="view-wrapper">
    <a-typography-title :level="4">Books</a-typography-title>

    <a-row :gutter="[10, 10]">
      <a-col :xs="12">
        <a-card hoverable size="small" @click="showDrawer">
          <template #cover>
            <img
              alt="book image"
              src="https://os.alipayobjects.com/rmsportal/QBnOOoLaAfKPirc.png"
            />
          </template>

          <a-card-meta title="Book Name" description="Book description">
            <!-- <template #description>www.instagram.com</template> -->
          </a-card-meta>
        </a-card>
      </a-col>

      <a-col :xs="12">
        <a-card hoverable size="small" @click="showDrawer">
          <template #cover>
            <img
              alt="book image"
              src="https://os.alipayobjects.com/rmsportal/QBnOOoLaAfKPirc.png"
            />
          </template>

          <a-card-meta title="Book Name" description="Book description">
            <!-- <template #description>www.instagram.com</template> -->
          </a-card-meta>
        </a-card>
      </a-col>
    </a-row>
  </div>

  <a-drawer title="Book Details" placement="bottom" height="85vh" :maskClosable="false" :open="drawerOpen" @close="closeDrawer">
    <a-row align="bottom" :gutter="[12, 24]">
      <a-col :span="12">
        <a-image
          src="https://zos.alipayobjects.com/rmsportal/jkjgkEfvpUPVyRjUImniVslZfWPnJuuZ.png"
        />
      </a-col>

      <a-col :span="12">
        <div>
          <a-typography-title :level="5">Book Title</a-typography-title>
          <a-typography-text type="secondary">Genre</a-typography-text>
        </div>
      </a-col>

      <a-col :span="24">
        <a-descriptions bordered size="small">
          <a-descriptions-item label="Publish Date">Cloud Database</a-descriptions-item>
          <a-descriptions-item label="Publisher">Prepaid</a-descriptions-item>
          <a-descriptions-item label="Pages">18:00:00</a-descriptions-item>
          <a-descriptions-item label="Author">$80.00</a-descriptions-item>
          <a-descriptions-item label="Description">$20.00</a-descriptions-item>
        </a-descriptions>
      </a-col>

      <a-col :span="24">
        <a-button block disabled type="primary" size="large">
          <template #icon>
            <SaveOutlined />
          </template>
          Save
        </a-button>
      </a-col>
    </a-row>
  </a-drawer>
</template>

<style scoped></style>
