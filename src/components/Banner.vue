<template>
  <div class="banner">
    <img v-bind:src="bannerSrc" :alt="banner.description">
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import json from '../resources/content.json';
@Component
export default class Banner extends Vue {
  data() {
    return {
      banner: json.Banner,
      bannerSrc: json.Banner.src
    }
  }
}
</script>

<style scoped lang="scss">
    @import "@/styles/_variables.scss";
    .banner {
      position: fixed;
      top: $header-h;
      img {
        width: 100%;
      }
    }
</style>
