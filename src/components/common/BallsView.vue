<template>
  <div class="divh">
      <Ball v-for="item in redsArray" v-bind:number = "item" v-bind:isRed = true v-bind:key="item"/>
      <Ball v-bind:number = blueNumber v-bind:isRed = false />
  </div>
</template>

<script>
import Ball from '../common/Ball.vue'

export default {
  name: 'BallsView',
  props: {
    redArray: Array,
    blue: Number
  },
  components: {
    Ball
  },
  computed: {
    redsArray: function () {
      return this.redArray
    },
    blueNumber: function() {
      return this.blue
    }
  }
}
</script>

<style scoped>
.divh{margin:0;}
</style>
