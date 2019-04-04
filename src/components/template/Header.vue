<template>
  <header>
      <nav>
         <h1 class="logo"><router-link to="/">Look After</router-link></h1>
         <ul>
             <li><a href="javascript:void(0)" class="login-link" title="Sing in">Login</a></li>
         </ul>
      </nav>
  </header>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Header extends Vue {
  @Prop() private user!: string;
}
</script>

<style scoped lang="scss">
    @import "@/styles/_variables.scss";
    header {
        position: sticky;
        top: 0;
        width: 100%;
        height: 50px;
        background: $tertiary-color;
    }
    .logo{
        display: inline-block;
        text-align: left;
        a {
            text-decoration: none;
            font-size: $title-size;
            color: $primary-color;
        }
    } 
</style>
