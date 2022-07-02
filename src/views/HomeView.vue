<template>
<div class="sample-page">
  <menux :list="list" @click-menu="onClickMenu"/>
</div>
</template>

<script setup>
import { ref } from 'vue';
import menux from '../components/menu';
const list = ref([
  {
    name: 'Home',
    path: '/'
  },
  {
    name: 'About',
    path: '/about'
  },
  {
    name: 'Contact',
    path: '/contact'
  },
  {
    name: 'Join Us',
    path: '/join'
  },
  {
    name: 'SiteMap',
    path: '/sitemap'
  },
  {
    name: 'Profile',
    path: '/porfile'
  }
]);

const onClickMenu = (menu) => {
  console.log(menu);
}
</script>

<style lang="less">
.sample-page {
  width: 100%;
}
</style>