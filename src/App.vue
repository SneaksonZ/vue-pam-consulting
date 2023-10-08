<template>
  <div id="app">
    <v-header/>
    <v-wrapper/>
  </div>
</template>

<script>
import vHeader from './components/header/v-header.vue';
import vWrapper from './components/v-wrapper.vue';
import { register } from 'swiper/element/bundle';

register();

export default {
  name: 'App',
  components: {
    vHeader,
    vWrapper
  }
}
</script>

<style>

</style>
