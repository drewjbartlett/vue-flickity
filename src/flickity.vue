<template>
  <div>
    <slot/>
  </div>
</template>

<script>
import Flickity from 'flickity';

export default {
  props: {
    options: Object,
  },

  mounted() {
    this.init();
  },

  beforeDestroy() {
    this.$flickity.destroy();
    this.$flickity = null;
  },

  methods: {
    /**
     * Initialize a new flickity and emit init event.
     */
    init() {
      this.$flickity = new Flickity(this.$el, this.options);
      this.$emit('init', this.$flickity);
    },

    /**
     * Return the current flickity instance to access directly
     *
     * @return {Flickity}
     */
    flickity() {
      return this.$flickity;
    },

    /**
     * Selecting Slides
     */

    /**
     * Select a slide
     *
     * @param {number} index
     * @param {boolean} isWrapped
     * @param {boolean} isInstant
     */
    select(index, isWrapped, isInstant) {
      this.$flickity.select(index, isWrapped, isInstant);
    },

    /**
     * Change to the next slide
     *
     * @param {boolean} isWrapped
     * @param {boolean} isInstant
     */
    next(isWrapped, isInstant) {
      this.$flickity.next(isWrapped, isInstant);
    },

    /**
     * Change to the previous slide
     *
     * @param {boolean} isWrapped
     * @param {boolean} isInstant
     */
    previous(isWrapped, isInstant) {
      this.$flickity.previous(isWrapped, isInstant);
    },

    /**
     * Select a cell
     *
     * @param {number} value
     * @param {boolean} isWrapped
     * @param {boolean} isInstant
     */
    selectCell(value, isWrapped, isInstant) {
      this.$flickity.selectCell(value, isWrapped, isInstant);
    },

    /**
     * Sizing and Positioning
     */

    /**
     * Trigger a resize event
     */
    resize() {
      this.$flickity.resize();
    },

    /**
     * Trigger a reposition event
     */
    reposition() {
      this.$flickity.reposition();
    },

    /**
     * Adding and removing cells
     */

    /**
     * Prepend elements to flickity
     *
     * @param {array|HTMLElement|NodeList} elements
     */
    prepend(elements) {
      this.$flickity.prepend(elements);
    },

    /**
     * Append elements to flickity
     *
     * @param {array|HTMLElement|NodeList} elements
     */
    append(elements) {
      this.$flickity.append(elements);
    },

    /**
     * Insert elements at a given index
     *
     * @param {array|HTMLElement|NodeList} elements
     * @param {number} index
     */
    insert(elements, index) {
      this.$flickity.insert(elements, index);
    },

    /**
     * Remove elements from flickity
     *
     * @param {array|HTMLElement|NodeList} elements
     */
    remove(elements) {
      this.$flickity.remove(elements);
    },

    /**
     * Player
     */

    /**
     * Trigger a playPlayer event
     */
    playPlayer() {
      this.$flickity.playPlayer();
    },

    /**
     * Trigger a stopPlayer event
     */
    stopPlayer() {
      this.$flickity.stopPlayer();
    },

    /**
     * Trigger a pausePlayer event
     */
    pausePlayer() {
      this.$flickity.pausePlayer();
    },

    /**
     * Trigger a unpausePlayer event
     */
    unpausePlayer() {
      this.$flickity.unpausePlayer();
    },

    /**
     * Trigger a rerender event
     */
    rerender() {
      this.$flickity.destroy();
      this.init();
    },

    /**
     * Utilities
     */

    /**
     * Destroy the flickity instance
     */
    destroy() {
      this.$flickity.destroy();
    },

    /**
     * Trigger a rerender event
     */
    reloadCells() {
      this.$flickity.reloadCells();
    },

    /**
     * Get the cell elements
     *
     * @return {array}
     */
    getCellElements() {
      return this.$flickity.getCellElements();
    },

    /**
     * Return flickity data
     *
     * @return {Flickity}
     */
    data() {
      return Flickity.data(this.$el);
    },

    /**
     * Events
     */

    /**
     * Attach an event
     *
     * @param {string} eventName
     * @param {function} listener
     */
    on(eventName, listener) {
      this.$flickity.on(eventName, listener);
    },

    /**
     * Remove an event
     *
     * @param {string} eventName
     * @param {function} listener
     */
    off(eventName, listener) {
      this.$flickity.off(eventName, listener);
    },

    /**
     * Attach an event once
     *
     * @param {string} eventName
     * @param {function} listener
     */
    once(eventName, listener) {
      this.$flickity.once(eventName, listener);
    },

    /**
     * Properties
     */

    /**
     * Return the selected element
     *
     * @return {HTMLElement}
     */
    selectedElement() {
      return this.$flickity.selectedElement;
    },

    /**
     * Return the selected elements
     *
     * @return {array}
     */
    selectedElements() {
      return this.$flickity.selectedElements;
    },

    /**
     * Return the selected index
     *
     * @return {number}
     */
    selectedIndex() {
      return this.$flickity.selectedIndex;
    },

    /**
     * Return the cells
     *
     * @return {array}
     */
    cells() {
      return this.$flickity.cells;
    },

    /**
     * Return the slides
     *
     * @return {array}
     */
    slides() {
      return this.$flickity.slides;
    },

    /**
     * Disable dragging of slider
     */
    disableDrag() {
      this.$flickity.options.draggable = false;
      this.$flickity.updateDraggable();
    },

    /**
     * Enable dragging of slider
     */
    enableDrag() {
      this.$flickity.options.draggable = true;
      this.$flickity.updateDraggable();
    },
  },

};
</script>

<style src="flickity/dist/flickity.css"></style>
