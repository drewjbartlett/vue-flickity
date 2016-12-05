# Flickity for Vue.js

## Vue support

Supports only Vue >= 2

## Installation and usage

See official documentation [here](http://flickity.metafizzy.co/).

    $ npm install vue-flickity

```javascript
import Slick from 'vue-slick';

new Vue({

    components: {
        Flickity
    },

    data () {
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
};
```

```html
<flickity ref="flickity" :options="flickityOptions">
    <div class="carousel-cell">1</div>
    <div class="carousel-cell">2</div>
    <div class="carousel-cell">3</div>
    <div class="carousel-cell">4</div>
    <div class="carousel-cell">5</div>
</flickity>

<button @click="previous()">Custom Previous Button</button>
<button @click="next()">Custom Next Button</button>
```
