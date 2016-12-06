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

    mounted() {
        this.flickity = new Flickity(this.$el, this.options);
    },

    beforeDestroy() {
        this.flickity.destroy();
        this.flickity = null;
    },

    methods: {
        next(isWrapped, isInstant) {
            this.flickity.next(isWrapped, isInstant);
        },

        previous(isWrapped, isInstant) {
            this.flickity.previous(isWrapped, isInstant);
        },

        select(index, isWrapped, isInstant) {
            this.flickity.select(index, isWrapped, isInstant);
        },

        selectCell(value, isWrapped, isInstant) {
            this.flickity.selectCell( value, isWrapped, isInstant );
        },

        resize() {
            this.flickity.resize();
        },

        reposition() {
            this.flickity.reposition();
        },

        prepend(elements) {
            this.flickity.prepend(elements);
        },

        append(elements) {
            this.flickity.append(elements);
        },

        insert(elements, index) {
            this.flickity.insert(elements, index);
        },

        remove(elements) {
            this.flickity.remove(elements);
        },

        playPlayer() {
            this.flickity.playPlayer();
        },

        stopPlayer() {
            this.flickity.stopPlayer();
        },

        pausePlayer() {
            this.flickity.pausePlayer();
        },

        unpausePlayer() {
            this.flickity.unpausePlayer();
        },

        destroy() {
            this.flickity.destroy();
        },

        reloadCells() {
            this.flickity.reloadCells();
        },

        getCellElements() {
            this.flickity.getCellElements();
        },

        data() {
            return Flickity.data(this.$el);
        }
    },

};
</script>
