<script setup>
import { h, ref } from 'vue'
import PhotosSlider from '../components/PhotosSlider.vue'
import AboutMe from '../components/AboutMe.vue'
import CSSMagic from '../components/CSSMagic.vue'
import VideoPlayer from '../components/VideoPlayer.vue'
const selectedKeys = ref(['photo'])
const items = ref([
  {
    key: 'photo',
    label: 'Фото',
    title: 'Фото'
  },
  {
    key: 'about',
    label: 'Обо мне',
    title: 'Обо мне'
  },
  {
    key: 'css',
    label: 'Фишка CSS',
    title: 'Фишка CSS'
  },
  {
    key: 'repo',
    label: h('a', { href: 'https://github.com/Synkov2102/practicum-test' }, 'Репозиторий'),
    title: 'Репозиторий'
  }
])
</script>

<template>
  <a-layout class="layout">
    <a-layout-header>
      <a-menu
        v-model:selectedKeys="selectedKeys"
        theme="dark"
        mode="horizontal"
        :items="items"
        :style="{ lineHeight: '64px' }"
      >
      </a-menu>
    </a-layout-header>
    <a-layout-content style="padding: 50px">
      <PhotosSlider v-if="selectedKeys[0] === 'photo'" />
      <AboutMe v-if="selectedKeys[0] === 'about'" />
      <CSSMagic v-if="selectedKeys[0] === 'css'" />
      <VideoPlayer v-if="selectedKeys[0] === 'css'" />
    </a-layout-content>
  </a-layout>
</template>

<style scoped>
.site-layout-content {
  min-height: 280px;
  padding: 24px;
  background: #fff;
}
#components-layout-demo-top .logo {
  float: left;
  width: 120px;
  height: 31px;
  margin: 16px 24px 16px 0;
  background: rgba(255, 255, 255, 0.3);
}
.ant-row-rtl #components-layout-demo-top .logo {
  float: right;
  margin: 16px 0 16px 24px;
}

[data-theme='dark'] .site-layout-content {
  background: #141414;
}
</style>
