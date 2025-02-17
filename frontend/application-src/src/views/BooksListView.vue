<script setup lang="ts"></script>

<template>
  <div class="view-wrapper">
    <a-typography-title :level="4">Books</a-typography-title>

    <a-row :gutter="[10, 10]">
      <a-col :xs="12">
        <a-card hoverable size="small">
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
        <a-card hoverable size="small">
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
</template>

<style scoped></style>
