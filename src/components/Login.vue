<template>
<div class="container">
  <button @click="showModal" class="login-link" value="Sing in">Login</button>
  <div class="login" v-if="show" v-on:change="showModal">
    <div class="aligner">
      <div class="aligner-item sing-in" v-if="singIn">
        <h4>{{ data.singin.title }}</h4>
        <p>{{ data.singin.text }}</p>
        <form>
          <div class="form-row">
            <input type="text" placeholder="E-mail" required>
          </div>
          <div class="form-row">
            <input type="password" placeholder="Password" required>
          </div>
          <div class="form-row">
            <button class="change-type" v-on:click="singIn = !singIn">Sing up</button>
            <button type="submit">Ok</button>
          </div>
        </form>
        <button class="close-modal" v-on:click="show = !show" value="x">X</button>
      </div>

      <div class="aligner-item sing-up" v-if="!singIn">
        <h4>{{ data.singup.title }}</h4>
        <p>{{ data.singup.text }}</p>
        <form>
          <div class="form-row">
            <input type="text" placeholder="Name" required>
          </div>
          <div class="form-row">
            <input type="text" placeholder="E-mail" required>
          </div>
          <div class="form-row">
            <input type="password" placeholder="Password" required>
          </div>
          <div class="form-row">
            <button class="change-type" v-on:click="singIn = !singIn">Sing in</button>
            <button type="submit">Ok</button>
          </div>
        </form>
        <button class="close-modal" v-on:click="show = !show" value="x">X</button>
      </div>
    </div>
  </div>
</div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';
import json from '@/resources/content.json';
const Login = Vue.extend({
    components: {
        
    },
    data() {
      return {
        show: false,
        singIn: true,
        data: json.Login
      }
    },
    methods: {
        showModal: function() {
          this.show = !this.show
        }
    },
    mounted() {
    }
})
export default Login;
</script>

<style scoped lang="scss">
    @import "@/styles/_mixins.scss";
    .login {
      position: fixed;
      top: 0;
      left: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      width: 100%;
      height: 100%;
      background: $tertiary-color;
      h4 {
        display: block;
        font-size: $ultra-size;
      }
      p {
        display: block;
        font-size: $tertiary-size;
        margin: 25px 0;
      }
    }
    .close-modal {
      position: fixed;
      right: 35px;
      top: 15px;
      font-size: $ultra-size;
      border: none;
      background: none;
    }
    .aligner {
      display: flex;
      width: 100%;
      max-width: 500px;
      align-items: center;
      justify-content: center;
    }
    .aligner-item {
      max-width: 50%;
    }
    .login-link {
      @include button;
      margin-top: 4px;
      float: right;
    }
    .form-row {
      margin-top: 10px;
      input {
        font-size: $secondary-size;
      }
    }
    form button {
      @include simple_button;
      width: 48%;
      &:first-child {
        margin-right: 4%; 
      }
    }
</style>
