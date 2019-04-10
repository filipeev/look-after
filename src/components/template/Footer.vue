<template>
  <footer>
    <div class="footer-container">
      <address>
        <span>{{ contact.text }} <a :href="mailto">{{ contact.email }}</a></span>
        <span>{{ contact.find_text }}<strong>{{ contact.address }}</strong></span>
      </address>
      <ul class="social">
        <li>
          <a href="https://www.facebook.com/" target="_blank">
           <svg version="1.1" id="Capa_1" 
              xmlns="http://www.w3.org/2000/svg" 
              xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" v-bind:width="iconSize" v-bind:height="iconSize" viewBox="0 0 49.652 49.652" style="enable-background:new 0 0 49.652 49.652;" xml:space="preserve">
              <g>
                <g>
                  <path d="M24.826,0C11.137,0,0,11.137,0,24.826c0,13.688,11.137,24.826,24.826,24.826c13.688,0,24.826-11.138,24.826-24.826
                  C49.652,11.137,38.516,0,24.826,0z M31,25.7h-4.039c0,6.453,0,14.396,0,14.396h-5.985c0,0,0-7.866,0-14.396h-2.845v-5.088h2.845
                  v-3.291c0-2.357,1.12-6.04,6.04-6.04l4.435,0.017v4.939c0,0-2.695,0-3.219,0c-0.524,0-1.269,0.262-1.269,1.386v2.99h4.56L31,25.7z
                  "/>
                </g>
              </g>
            </svg>
          </a>
        </li>
        <li>
          <a href="https://www.instagram.com/" target="_blank">
            <svg version="1.1" id="Capa_1" 
              xmlns="http://www.w3.org/2000/svg" 
              xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" v-bind:width="iconSize" v-bind:height="iconSize" viewBox="0 0 49.652 49.652" style="enable-background:new 0 0 49.652 49.652;" xml:space="preserve">
              <g>
                <g>
                  <g>
                    <path d="M24.825,29.796c2.739,0,4.972-2.229,4.972-4.97c0-1.082-0.354-2.081-0.94-2.897c-0.903-1.252-2.371-2.073-4.029-2.073
                    c-1.659,0-3.126,0.82-4.031,2.072c-0.588,0.816-0.939,1.815-0.94,2.897C19.854,27.566,22.085,29.796,24.825,29.796z"/>
                    <polygon points="35.678,18.746 35.678,14.58 35.678,13.96 35.055,13.962 30.891,13.975 30.907,18.762 			"/>
                    <path d="M24.826,0C11.137,0,0,11.137,0,24.826c0,13.688,11.137,24.826,24.826,24.826c13.688,0,24.826-11.138,24.826-24.826
                    C49.652,11.137,38.516,0,24.826,0z M38.945,21.929v11.56c0,3.011-2.448,5.458-5.457,5.458H16.164
                    c-3.01,0-5.457-2.447-5.457-5.458v-11.56v-5.764c0-3.01,2.447-5.457,5.457-5.457h17.323c3.01,0,5.458,2.447,5.458,5.457V21.929z" />
                    <path d="M32.549,24.826c0,4.257-3.464,7.723-7.723,7.723c-4.259,0-7.722-3.466-7.722-7.723c0-1.024,0.204-2.003,0.568-2.897
                    h-4.215v11.56c0,1.494,1.213,2.704,2.706,2.704h17.323c1.491,0,2.706-1.21,2.706-2.704v-11.56h-4.217
                    C32.342,22.823,32.549,23.802,32.549,24.826z"/>
                  </g>
                </g>
              </g>
            </svg>
          </a>
        </li>
        <li>
          <a href="https://www.youtube.com/" target="_blank">
            <svg version="1.1" id="Capa_1" 
              xmlns="http://www.w3.org/2000/svg" 
              xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" v-bind:width="iconSize" v-bind:height="iconSize" viewBox="0 0 511.626 511.627" style="enable-background:new 0 0 21 21;" xml:space="preserve">
              <g>
                <path d="M511.339,212.987c-0.186-10.277-1-23.271-2.423-38.97c-1.431-15.708-3.478-29.746-6.14-42.115
                c-3.046-13.893-9.661-25.6-19.842-35.117c-10.181-9.519-22.031-15.037-35.549-16.562c-42.258-4.755-106.115-7.135-191.573-7.135
                c-85.459,0-149.317,2.38-191.572,7.135c-13.516,1.524-25.319,7.043-35.404,16.562c-10.089,9.514-16.656,21.221-19.702,35.117
                c-2.852,12.373-4.996,26.41-6.423,42.115c-1.425,15.699-2.235,28.688-2.424,38.97C0.094,223.265,0,237.539,0,255.813
                c0,18.272,0.094,32.55,0.288,42.826c0.189,10.284,0.999,23.271,2.424,38.969c1.427,15.707,3.474,29.745,6.139,42.116
                c3.046,13.897,9.659,25.602,19.842,35.115c10.185,9.517,22.036,15.036,35.548,16.56c42.255,4.76,106.109,7.139,191.572,7.139
                c85.466,0,149.315-2.379,191.573-7.139c13.518-1.523,25.316-7.043,35.405-16.56c10.089-9.514,16.652-21.225,19.698-35.115
                c2.854-12.371,4.996-26.409,6.427-42.116c1.423-15.697,2.231-28.691,2.423-38.969c0.191-10.276,0.287-24.554,0.287-42.826
                C511.626,237.539,511.531,223.265,511.339,212.987z M356.883,271.231L210.706,362.59c-2.666,1.903-5.905,2.854-9.71,2.854
                c-2.853,0-5.803-0.764-8.848-2.286c-6.28-3.422-9.419-8.754-9.419-15.985V164.454c0-7.229,3.14-12.561,9.419-15.986
                c6.473-3.431,12.657-3.239,18.558,0.571l146.178,91.36c5.708,3.23,8.562,8.372,8.562,15.415
                C365.446,262.854,362.591,267.998,356.883,271.231z"/>
              </g>
            </svg>
          </a>
        </li>
      </ul>
    </div>
  </footer>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import json from '@/resources/content.json';
@Component
export default class Footer extends Vue {
  data() {
    return {
      mailto: "mailto:" + json.Contact.email,
      contact: json.Contact,
      iconSize: '35px'
    }
  }
}
</script>

<style scoped lang="scss">
  @import "@/styles/_mixins.scss";
  footer {
    display: block;
    position: relative;
    width: 100%;
    padding: $footer-h 0;
    background: $tertiary-color; 
    @include desktop {
      display: table;
      width: 100%;
    }
    .footer-container {
      max-width: 1000px;
      margin: 0 auto;
    }
  }
  address {
    line-height: 1.4em;
    @include desktop {
      float: left;
    }
    span {
      display: block;
      margin-bottom: 10px;
    }
    a {
      color: $primary-color;
    }
    strong {
      display: block;
      font-weight: 600;
    }
  }
  .social {
    margin: 15px auto;
    @include desktop {
      float: right;
    }
    li {
      display: inline-block;
      margin: 5px;
      a {
        text-indent: -9999px;
        font-size: 0;
        &:hover {
          svg {
            opacity: 0.7;
          }
        }
      }
      svg {
        transition: all .5s;
        fill: $primary-color;
        opacity: 1;
      }
    }
  }
</style>
