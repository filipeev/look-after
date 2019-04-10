<template>
  <section class="about-us">
    <h2>{{ data.title }} <strong>{{ data.detail }}</strong></h2>
    <p>{{ data.description }}</p>
  </section>
</template>

<script>
import { Component, Vue } from 'vue-property-decorator';
import json from '../resources/content.json';

@Component
export default class Description extends Vue {
  data() {
    return {
      data: json.Description
    }
  }
}
</script>

<style scoped lang="scss">
    @import "@/styles/_mixins.scss";
    
    .about-us {
      position: relative;
      padding: 100px 30px;
      margin-top: 109px;
      z-index: 200;
      background: $tertiary-color;
      text-align: center;
      @include tablet {
        margin-top: 209px;
      }
      @include desktop {
        margin-top: 360px;
      }
    }
    h2 {
      font-size: $ultra-size;
      margin-bottom: 25px;
      opacity: 0.5;
      line-height: 1.3em;
      font-family: $main-font;
      strong {
        display: block;
        text-transform: uppercase;
        color: $primary-color;
      }
    }
    p {
      color: $secondary-color;
      font-size: $tertiary-size;
      line-height: 1.4em;
      max-width: 600px;
      margin: 0 auto;
    }
</style>
