<template>
  <footer>
      <address>
        Voce pode contatar o autor em <a href="http://www.somedomain.com/contact">www.somedomain.com</a>.<br>
        Se encontrar qualquer bug, por favor <a href="mailto:webmaster@somedomain.com">contate o administrador do site</a>.<br>
        Você tambem pode querer nos visitar:<br>
        Mozilla Foundation<br>
        1981 Landings Drive<br>
        Building K<br>
        Mountain View, CA 94043-0801<br>
        USA
      </address>
  </footer>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class Footer extends Vue {}
</script>

<style lang="scss">
  @import "@/styles/_variables.scss";
  footer {
    width: 100%;
    height: 50px;
    background: $secondary-color;
  }
</style>
