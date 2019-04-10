<template>
  <div class="banner">
    <img v-bind:src="bannerSrc" :alt="banner.description">
  </div>
</template>

<script>
import { Component, Vue } from 'vue-property-decorator';
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
      width: 100%;
      top: $header-h;
      img {
        min-height: 80px;
        max-width: 120%;
        margin: 0 auto;
      }
    }
</style>
