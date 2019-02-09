<template>
  <div>
    <slot name="learn"/>
    <h1>I am from Hello World.</h1>
    <slot name="app"></slot>

    <hr>

    <h1>Let's learn transition</h1>

    <button @click="transitionGuy = ! transitionGuy">Transition Button</button>
    <transition name="fade">
      <p v-if="transitionGuy">hello</p>
    </transition>

    <hr>
    <h1>Flip List Awesome</h1>
    <div id="flip-list-demo" class="demo">
      <button v-on:click="shuffle">Shuffle</button>
      <transition-group name="flip-list" tag="ul">
        <li v-for="item in items" v-bind:key="item">{{ item }}</li>
      </transition-group>
    </div>


    <hr>
    <hr>
    Trying out mixins
    <div v-for="item in itemForMixins">
        {{item}}
    </div>
  </div>
</template>
<script>
import lodash from "lodash";
import itemSuffle from '../mixins/mixins';
export default {
  data() {
    return {
      test: "Hii",
      transitionGuy: false,
      items: [1, 2, 3, 4, 5, 6, 7, 8, 9]
    };
  },
  methods: {
     shuffle: function() {
      this.items = _.shuffle(this.items);
    }
  },
  props: ["msg"],
  mixins: [itemSuffle]
};
</script>

<style>
h1 {
  color: blue;
}
.flip-list-move {
  transition: transform 1s;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
