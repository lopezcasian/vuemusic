<template lang="pug">
  li.artist
    p {{ artist.listeners | formatNumber }} listeners
    img(:src="artist.image[2]['#text']")
    h3: a(v-bind:href="artist.url" target="_blank") {{ artist.name }}
</template>

<script>
let numeral = require("numeral");

export default {
  name: 'artist',
  props: ['artist'],
  filters: {
    formatNumber: function(number){
      return numeral( number ).format("0,0")
    }
  }
}
</script>

<style lang="stylus" scoped>
li.artist
  display inline-block
  margin 10px 10px
</style>
