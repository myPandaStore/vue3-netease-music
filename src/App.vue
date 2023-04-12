<script setup lang="ts">
import {  RouterView } from 'vue-router'
import musicHeader from "./components/Header/music-header.vue"
import musicFooter from './components/Footer/music-footer.vue';

</script>

<template>
  <musicHeader />
  <RouterView />
  <musicFooter />
</template>

<style>
body {
  font: 12px/1.3 "Microsoft YaHei", Tahoma, Helvetica, Arial, "\5b8b\4f53", sans-serif;
  color: #333;
  margin: 0;
  padding: 0;
  min-width: 1380px;
}
</style>
