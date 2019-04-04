<template>
  <div class="banner">

  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Banner extends Vue {
  @Prop() private quantity!: number;
}
</script>

<style scoped lang="scss">
    @import "@/styles/_variables.scss";
    
</style>
