<script setup lang="ts">
import { ConfigProvider } from 'ant-design-vue';
import MainLayout from './layouts/MainLayout.vue';
</script>

<template>
  <ConfigProvider>
    <MainLayout />
  </ConfigProvider>
</template>

<style>
#app {
  width: 100vw;
  height: 100vh;
}
</style>