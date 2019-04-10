<template>
  <div class="about">
    <div class="banner-msg">
      <ul class="infos" v-if="userLogged">
        <li>{{ data.user.name }}<strong>{{ userLogged.name }}</strong><br />{{ data.text }}</li>
        <li>{{ data.user.email }}<strong>{{ userLogged.email }}</strong></li>
        <li>{{ data.user.register }}<strong>{{ userLogged.registered }}</strong></li>
        <li>{{ data.user.phone }}<strong>{{ userLogged.phone }}</strong></li>
      </ul>
      <h4>{{ data.title }}</h4>
      <button value="Home"><router-link to="/">Home</router-link></button>
    </div>
  </div>
</template>

<script>
import { Vue } from 'vue-property-decorator';
import json from '@/resources/content.json'
const About = Vue.extend({
    components: {
        
    },
    data() {
      return {
        user: null,
        logged: null,
        userLogged: null,
        data: json.About
      }
    },
    methods: {
      getUser: function() {
        let data = JSON.parse(this.logged);
        if(data){
          this.userLogged = data; 
        }
      }
  },
  mounted() {
    this.logged = localStorage.getItem('user');
    if(this.logged){
      this.getUser();
    }
  }
})
export default About;
</script>

<style scoped lang="scss">
    @import "@/styles/_mixins.scss";

    .about {
      width: 100%;
      button,
      a {
        @include simple_button;
      }
    }
    .infos {
      font-size: $title-size;
      margin: 50px 0;
      li {
        line-height: 35px;
        color: $secondary-color;
      }
    }
    h4 {
      display: block;
      margin-bottom: 50px;
    }
    .banner-msg {
      width: 100%;
      padding: 30px;
      box-sizing: content-box;
      text-align: center;
      font-size: $extreme-size;
      background: $tertiary-color;
      padding: 20px 0;
      font-family: $secondary-color;
      color: $primary-text;
    }
</style>

