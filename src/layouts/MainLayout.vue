<script setup lang="ts">
import { ref } from 'vue';
import { Layout, Menu } from 'ant-design-vue';
import { useI18n } from 'vue-i18n';
import { useRouter } from 'vue-router';

const { t } = useI18n();
const router = useRouter();
const collapsed = ref(false);

const menuItems = [
  {
    key: 'dashboard',
    title: t('menu.dashboard'),
    path: '/'
  },
  {
    key: 'videoProcessing',
    title: t('menu.videoProcessing'),
    path: '/video-processing'
  },
  {
    key: 'settings',
    title: t('menu.settings'),
    path: '/settings'
  }
];

const handleMenuClick = ({ key }: { key: string }) => {
  const item = menuItems.find(item => item.key === key);
  if (item) {
    router.push(item.path);
  }
};
</script>

<template>
  <Layout style="min-height: 100vh">
    <Layout.Sider v-model:collapsed="collapsed" collapsible>
      <div class="logo" />
      <Menu
        theme="dark"
        mode="inline"
        :selectedKeys="[$route.name as string]"
        @click="handleMenuClick"
      >
        <Menu.Item v-for="item in menuItems" :key="item.key">
          {{ item.title }}
        </Menu.Item>
      </Menu>
    </Layout.Sider>
    <Layout>
      <Layout.Header style="background: #fff; padding: 0" />
      <Layout.Content style="margin: 0 16px">
        <router-view />
      </Layout.Content>
    </Layout>
  </Layout>
</template>

<style scoped>
.logo {
  height: 32px;
  margin: 16px;
  background: rgba(255, 255, 255, 0.3);
}
</style>