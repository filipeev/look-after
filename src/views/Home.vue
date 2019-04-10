<template>
  <div class="home">
    <Banner />
    <Description />
    <Carousel />
    <Contact />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Banner from '@/components/Banner.vue'; // @ is an alias to /src
import Description from '@/components/Description.vue';
import Carousel from '@/components/Carousel.vue';
import Contact from '@/components/Contact.vue';

@Component({
  components: {
    Banner,
    Description,
    Carousel,
    Contact,
  },
})
export default class Home extends Vue {
  data () {
    return {
      quantity: 4
    }
  }
}
</script>

<style lang="scss">
    @import "@/styles/_styles.scss";

    .home {
      width: 100%;
    }
</style>

