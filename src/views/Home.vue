<template>
  <div class="home">
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Banner from '@/components/Banner.vue'; // @ is an alias to /src

@Component({
  components: {
    Banner,
  },
})
export default class Home extends Vue {}
</script>
