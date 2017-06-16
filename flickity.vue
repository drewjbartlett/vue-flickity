<template>
    <div>
        <slot></slot>
    </div>
</template>

<script>
import Flickity from 'flickity';

export default {
    props: {
        options: {
            type: Object,

            default () {
                return {};
            }
        },
    },

    mounted () {
      this.init();
    },

    beforeDestroy () {
        this.flickity.destroy();
        this.flickity = null;
    },

    methods: {
        init() {
            this.flickity = new Flickity(this.$el, this.options);
        },

        next (isWrapped, isInstant) {
            this.flickity.next(isWrapped, isInstant);
        },

        previous (isWrapped, isInstant) {
            this.flickity.previous(isWrapped, isInstant);
        },

        select (index, isWrapped, isInstant) {
            this.flickity.select(index, isWrapped, isInstant);
        },

        selectedIndex () {
            return this.flickity.selectedIndex
        },

        selectCell (value, isWrapped, isInstant) {
            this.flickity.selectCell( value, isWrapped, isInstant );
        },

        resize () {
            this.flickity.resize();
        },

        reposition () {
            this.flickity.reposition();
        },

        prepend (elements) {
            this.flickity.prepend(elements);
        },

        append (elements) {
            this.flickity.append(elements);
        },

        insert (elements, index) {
            this.flickity.insert(elements, index);
        },

        remove (elements) {
            this.flickity.remove(elements);
        },

        playPlayer () {
            this.flickity.playPlayer();
        },

        stopPlayer () {
            this.flickity.stopPlayer();
        },

        pausePlayer () {
            this.flickity.pausePlayer();
        },

        unpausePlayer () {
            this.flickity.unpausePlayer();
        },

        rerender () {
            this.flickity.destroy();
            this.init();
        },

        destroy () {
            this.flickity.destroy();
        },

        reloadCells () {
            this.flickity.reloadCells();
        },

        getCellElements () {
            this.flickity.getCellElements();
        },

        data () {
            return Flickity.data(this.$el);
        },

        on (eventName, listener) {
            this.flickity.on(eventName, listener);
        },

        off (eventName, listener) {
            this.flickity.off(eventName, listener);
        },

        once (eventName, listener) {
            this.flickity.once(eventName, listener);
        }
    },

};
</script>
