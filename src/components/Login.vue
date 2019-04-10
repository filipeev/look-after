<template>
<div class="container">
  <button @click="showModal" v-if="logged == null" class="login-link" value="Sing in">Login</button>
  <div class="welcome-box" v-if="logged != null">
    <span>Welcome, {{ userLogged }}</span>
    <button class="login-link" value="About"><router-link to="/About">About</router-link></button>
    <button @click="logOut" class="login-link" value="logout">Log Out</button>
  </div>
  <div class="login" v-if="show">
    <div class="aligner">
      <div class="aligner-item sing-in" v-if="singIn">
        <h4>{{ data.singin.title }}</h4>
        <p>{{ data.singin.text }}</p>
        <form id="loginForm" @submit="loginForm">
          <div class="form-row">
            <input type="text" v-model="emailLogin" placeholder="E-mail" required>
          </div>
          <div class="form-row">
            <input type="password" v-model="passwordLogin" placeholder="Password" required>
          </div>
          <div class="form-row">
            <button class="change-type" @click="singIn = !singIn">Sing up</button>
            <button type="submit">Ok</button>
          </div>
        </form>
        <button class="close-modal" @click="show = !show" value="x">X</button>
      </div>

      <div class="aligner-item sing-up" v-if="!singIn">
        <h4>{{ data.singup.title }}</h4>
        <p>{{ data.singup.text }}</p>
        <form id="registerForm" @submit="registerForm">
          <div class="form-row">
            <input type="text" v-model="nameRegister" placeholder="Name" required>
          </div>
          <div class="form-row">
            <input type="text" v-model="emailRegister" placeholder="E-mail" required>
          </div>
          <div class="form-row">
            <input type="text" v-model="phoneRegister" max="9" placeholder="Phone" required>
          </div>
          <div class="form-row">
            <input type="password" v-model="passRegister" placeholder="Password" required>
          </div>
          <div class="form-row">
            <button class="change-type" @click="singIn = !singIn">Sing in</button>
            <button type="submit">Ok</button>
          </div>
        </form>
        <button class="close-modal" @click="show = !show" value="x">X</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
import { Vue } from 'vue-property-decorator';
import json from '@/resources/content.json';
import users from '@/resources/users.json';
const Login = Vue.extend({
    components: {
        
    },
    data() {
      return {
        emailLogin: null,
        passwordLogin: null,
        nameRegister: null,
        emailRegister: null,
        phoneRegister: null,
        passRegister: null,
        errors: null,
        show: false,
        singIn: true,
        data: json.Login,
        users: users.Accounts.users,
        user: null,
        logged: null,
        userLogged: null
      }
    },
    methods: {
      showModal: function() {
        this.show = !this.show
      },
      logOut: function() {
        localStorage.setItem('user', null);
        this.logged = null;
        this.userLogged = null;
      },
      loginForm: function (e) {
        if (this.emailLogin && this.passwordLogin) {
          const auth = this.users.filter((x) => { return (
              x.email == this.emailLogin && x.password == this.passwordLogin 
            )
          });
          if (auth) {
            const objct = auth[0];
            const user = {
              "email": objct.email,
              "name": objct.name,
              "phone": objct.phone,
              "password": objct.password
            }
            localStorage.setItem('user', JSON.stringify(user));
            this.user = user;
            this.logged = true;
            this.userLogged = this.user.name;
            this.show = false;
          }
          return this.logged;
        }
      },
      registerForm: function (e) {
        if (this.emailRegister && this.nameRegister && this.phoneRegister && this.passRegister) {
          const user = {
            "email": this.emailRegister,
            "name": this.nameRegister,
            "phone": this.phoneRegister,
            "password": this.passRegister
          }
          localStorage.setItem('user', JSON.stringify(user));
          this.user = user;
          this.logged = true;
          this.userLogged = this.user.name;
          this.show = false;
          return true;
        }
      },
      getUser: function() {
        let data = JSON.parse(this.logged);
        if(data){
          this.userLogged = data.name; 
        }
      }
  },
  mounted() {
    this.logged = localStorage.getItem('user');
      this.getUser();
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
      outline: none;
    }
    .aligner {
      display: flex;
      width: 80%;
      align-items: center;
      justify-content: center;
    }
    .aligner-item {
      width: 80%;
      max-width: 500px;
    }
    .welcome-box {
      width: 100%;
      display: table;
      position: absolute;
      right: 15px;
      span {
        display: none;
      }
      button {
        font-size: $primary-size;
        letter-spacing: 1px;
        padding: 5px;
      }
      @include desktop {
        display: flex;
        float: right;
        position: static;
        width: auto;
        button {
          padding: 5px 15px;
        }
        span {
          vertical-align: middle;
          padding-right: 20px;
          display: flex;
          float: left;
          line-height: 46px;
        }
      }
      @include tablet {
        display: flex;
        float: right;
        position: static;
        width: auto;
        button {
          padding: 5px 15px;
        }
        span {
          vertical-align: middle;
          padding-right: 20px;
          display: flex;
          float: left;
          line-height: 46px;
        }
      }
      button {
        margin-left: 15px;
      }
    }
    .login-link {
      @include button;
      margin-top: 4px;
      float: right;
      & > * {
        color: $primary-text;
        text-decoration: none;
      }
    }
    .form-row {
      margin-top: 10px;
      input {
        font-size: $secondary-size;
      }
    }
    form {
      input {
        background: rgba(255, 255, 255, 0.66);
        border: none;
      }
      button {
        @include simple_button;
        width: 48%;
        &:first-child {
          margin-right: 4%; 
        }
      }
    }
</style>
