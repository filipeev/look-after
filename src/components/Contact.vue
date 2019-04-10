<template>
  <section class="contact">
    <h2>Need something ?</h2>
    <p>Send a message and we'll be in touch soon</p>
    <form>
      <div class="form-row">
        <input type="text" placeholder="Name" required>
      </div>
      <div class="form-row">
        <input type="text" placeholder="E-mail" required>
      </div>
      <div class="form-row select-form">
        <select name="subject" id="subject">
          <option selected value="review">Review</option>
          <option value="order">Missing product</option>
          <option value="soubt">Doubts</option>
          <option value="complain">Complain</option>
          <option value="other">Other</option>
        </select>
      </div>
      <div class="form-row">
        <textarea name="message" id="contact-message" cols="30" rows="10" placeholder="Your message"></textarea>
      </div>
      <div class="form-row">
        <button type="submit">Send</button>
      </div>
    </form>
  </section>
</template>

<script>
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class Contact extends Vue {}
</script>

<style scoped lang="scss">
    @import "@/styles/_mixins.scss";
    
    .contact {
      position: relative;
      margin: 0;
      z-index: 200;
      width: 100%;
      color: $secondary-color;
      padding: 50px $safe-space;
      box-sizing: border-box;
      background: #fff;
    }
    h2 {
      font-size: $ultra-size;
      margin-bottom: 10px;
    }
    p {
      font-size: $tertiary-size;
      margin-bottom: 25px;
    }
    form {
      width: 100%;
      max-width: 600px;
      box-sizing: border-box;
      margin: 0 auto;
      .form-row {
        margin: 10px 0;
      }
      input,
      select {
        font-size: $secondary-size;
      }
      textarea {
        font-size: $secondary-size;
        height: 200px;
      }
      button {
        @include button;
        width: 100%;
      }
    }
</style>
