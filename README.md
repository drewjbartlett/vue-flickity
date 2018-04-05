# Flickity for Vue.js

[![npm](https://img.shields.io/npm/v/vue-flickity.svg?style=flat-square)](https://www.npmjs.com/package/vue-flickity)
[![npm](https://img.shields.io/npm/dt/vue-flickity.svg?style=flat-square)](https://www.npmjs.com/package/vue-flickity)
[![npm](https://img.shields.io/travis/drewjbartlett/vue-flickity.svg?branch=master&style=flat-square)](https://www.npmjs.com/package/vue-flickity)

A Vue Component for Flickity.js - See a live demo [here](http://drewjbartlett.com/demos/vue-flickity/).

<p align="center">
    <img width="200" src="http://flickity.metafizzy.co/img/flickity-illustration.gif" alt="Flickity">
    <img width="200" src="https://vuejs.org/images/logo.png" alt="Vue.js">
</p>

## Vue support

Supports only Vue >= 2

## Installation and usage

See official documentation [here](http://flickity.metafizzy.co/).

  $ npm install vue-flickity --save

```javascript
import Flickity from 'vue-flickity';

new Vue({
  components: {
    Flickity
  },

  data() {
    return {
      flickityOptions: {
      initialIndex: 3,
      prevNextButtons: false,
      pageDots: false,
      wrapAround: true

      // any options from Flickity can be used
      }
    }
  },

  methods: {
    next() {
      this.$refs.flickity.next();
    },

    previous() {
      this.$refs.flickity.previous();
    }
  }
});
```

```html
<flickity ref="flickity" :options="flickityOptions">
  <div class="carousel-cell">1</div>
  <div class="carousel-cell">2</div>
  <div class="carousel-cell">3</div>
  <div class="carousel-cell">4</div>
  <div class="carousel-cell">5</div>
</flickity>

<!-- if you don't want to use the buttons Flickity provides -->
<button @click="previous()">Custom Previous Button</button>
<button @click="next()">Custom Next Button</button>
```
