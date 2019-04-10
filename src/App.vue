<template>
  <div id="app">
    <Header/>
    <router-view/>
    <Footer/>
  </div>
</template>

// SCRIPTS
<script>
  import { Component, Vue } from 'vue-property-decorator';
  import Header from '@/components/template/Header.vue';
  import Footer from '@/components/template/Footer.vue';

  @Component({
    components: {
      Header,
      Footer,
    },
  })

  export default class App extends Vue {}
</script>

// STYLES
<style lang="scss">
@import "@/styles/_reset.scss";
@import "@/styles/_variables.scss";
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
