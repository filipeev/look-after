<template>
  <div class="wrapper">
    <carousel-component>
      <carousel-item v-for="products in items" v-bind:key="products.items">
        <div v-for="product in products.product" v-bind:key="product.product" class="product">
          <img :src="product.src" :alt="product.description">
          <strong>Diaper sample</strong>
          <span>Size: 6 lbs (2.7 kg)	Swaddlers Preemie</span>
        </div>
      </carousel-item>
    </carousel-component>
  </div>
</template>

<script>
import { Vue } from 'vue-property-decorator';
import json from '../resources/carousel.json';

Vue.component('carousel-component', {
  render: function (createElement) {
    return createElement('div', 
      { class: 'carousel-component' },
      this.items.map((item, index) =>
        createElement('div', {
          'class': 'carousel-page' + (this.current === index ? ' active' : ''),
          on: { 
            mouseover: () => { this.mouseOver(); },
            mouseleave: () => { this.mouseOut(); }
          },
          style: {
            transform: `translate3d(${this.position(index) * 100}%, 0, 0)`,
          }
        }, [item])
      ).concat([
        createElement('button', {
          'class': 'carousel-nav-prev',
          on: { click: () => { this.decreaseCurrent(); }}
        }, 'Prev'),
        createElement('button', {
          'class': 'carousel-nav-next',
          on: { click: () => { this.increaseCurrent(); } }
        }, 'Next')
      ])
    );
  },
  data: function() {
    return {
      hover: false,
      auto: true,
      timer: null,
      current: 0
    };
  },
  computed: {
    items: function() {
      return this.$slots.default.filter(function(item) {
        return item.componentOptions !== undefined &&
          item.componentOptions.tag === 'carousel-item';
      });
    }
  },
  methods: {
    autoPlay: function(locked) {
      clearTimeout(this.timer);
      if(this.auto && !this.hover){
        this.timer = setTimeout(() => {
          this.increaseCurrent();
          this.autoPlay(this.hover);
        }, 2000);
      }
    },
    mouseOut: function() {
      this.hover = false;
      setTimeout(() => {
        this.autoPlay(true);
      }, 1000);
    },
    mouseOver: function() {
      clearTimeout(this.timer);
      this.hover = true;
    },
    decreaseCurrent: function() {
      this.current += this.items.length - 1;
      this.current %= this.items.length;
    },
    increaseCurrent: function() {
      this.current += 1;
      this.current %= this.items.length;
    },
    position: function(index) {
      if (index === this.current) return 0;
      if (index === (this.current + 1) % this.items.length) return 1;
      return -1;
    }
  },
  mounted() {
    this.autoPlay(this.auto);
  }
});

Vue.component('carousel-item', {
  render: function (createElement) {
    return createElement('div', { class: 'carousel-item' }, this.$slots.default);
  }
});

const Carousel = Vue.extend({
  props: {
    
  },
  data() {
    return {
      hover: false,
      quantity: json.Carousel.show,
      items: json.Carousel.items,
      data: json
    }
  }
})

export default Carousel;
</script>

<style lang="scss">
  @import "@/styles/_mixins.scss";

      
.wrapper {
  width: 100%;
  position: relative;
  overflow: hidden;
  margin: 0 auto;
  padding: 55px 0;
  background: white;
  border-bottom: 1px solid #EEE;
}

.carousel-component {
  position: relative;
  overflow: hidden;
  max-width: 1100px;
  margin: 0 auto;
}

.carousel-page {
  visibility: hidden;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  transition: 0.5s;
  padding: 10px;
  box-sizing: border-box;
  &.active {
    visibility: visible;
    position: static;
  }

  h2 {
    margin: 0;
  }
}

.carousel-item {
  .product {
    display: inline-block;
    width: 100%;
    vertical-align: top;
    @include tablet {
      width: 50%;
    }
    @include desktop {
      width: 50%;
    }
    img {
      max-width: 150px;
      max-height: 150px;
      @include desktop {
        max-width: 250px;
        max-height: 250px;
      }
    }
    strong {
      display: block;
      font-weight: bold;
      font-size: $tertiary-size;
    }
  }
}

.carousel-nav-prev,
.carousel-nav-next {
  position: absolute;
  top: 50%;
  transform: translate(0, -50%);
  display: block;
  width: 50px;
  height: 50px;
  border: 0;
  background: transparent;
  color: transparent;
  font-size: 0;
  outline: none;
  cursor: pointer;
}

.carousel-nav-prev {
  left: $safe-space;
  border-top: $caorusel-size solid transparent;
  border-bottom: $caorusel-size solid transparent;
  border-right:$caorusel-size solid $primary-color;
}

.carousel-nav-next {
  right: $safe-space;
  border-top: $caorusel-size solid transparent;
  border-bottom: $caorusel-size solid transparent;
  border-left: $caorusel-size solid $primary-color;
}
</style>
