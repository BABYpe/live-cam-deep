<script setup lang="ts">
import { Card } from 'ant-design-vue';
</script>

<template>
  <div class="dashboard">
    <h2>Dashboard</h2>
    <div class="dashboard-grid">
      <Card title="Video Processing Status">
        <p>Ready for processing</p>
      </Card>
      <Card title="System Status">
        <p>All systems operational</p>
      </Card>
    </div>
  </div>
</template>

<style scoped>
.dashboard {
  padding: 24px;
}

.dashboard-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 16px;
  margin-top: 16px;
}
</style>