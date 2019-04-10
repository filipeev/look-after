<template>
    <header>
        <nav>
            <div class="container">
                <h1 class="logo"><router-link to="/">Look After</router-link></h1>
                <ul>
                    <li><a href="javascript:void(0)" class="login-link" title="Sing in">Login</a></li>
                </ul>
            </div>
        </nav>
    <Login />
    </header>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import { Login } from '@/components/Login.vue';

@Component({
  components: {
    Login,
  },
})
export default class Header extends Vue {
  @Prop() private user!: string;
}
</script>

<style scoped lang="scss">
    @import "@/styles/_mixins.scss";
    header {
        position: sticky;
        top: 0;
        display: table;
        width: 100%;
        background: #ffffff;
        box-shadow: 0px -4px 11px 8px #ccc4c4;
        padding: 8px 0;
        z-index: 2000;
    }
    .container {
        max-width:  1000px;
        margin: 0 auto;
    }
    nav {
        padding: 0 $safe-space;
    }
    .logo{
        line-height: 50px;
        display: inline-block;
        text-align: left;
        float: left;
        a {
            text-decoration: none;
            font-size: $title-size;
            color: $primary-color;
        }
    }
    .login-link {
        @include button;
        margin-top: 8px;
        float: right;
    }
</style>
