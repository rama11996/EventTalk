<template lang="pug">
section.sponsors
  .container
    h2 Sponsors
    p Conferences Deticated to building remarkable events
    ul.item-list
      li.sponsor-item(v-for="(s, i) in sponsors", :key="i")
        .thumb
          img(:src="s.image")
    .cta
      a.btn.btn-primary View All Sponsors
</template>
<script>
export default {
  data () {
    return {
      sponsors: [
        {
          image: 'images/sponsors/sponsor1.png'
        },
        {
          image: 'images/sponsors/sponsor2.png'
        },
        {
          image: 'images/sponsors/sponsor3.png'
        },
        {
          image: 'images/sponsors/sponsor4.png'
        },
        {
          image: 'images/sponsors/sponsor5.png'
        },
        {
          image: 'images/sponsors/sponsor6.png'
        },
        {
          image: 'images/sponsors/sponsor7.png'
        },
        {
          image: 'images/sponsors/sponsor8.png'
        },
        {
          image: 'images/sponsors/sponsor8.png'
        },
      ]
    }
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'

section.sponsors
  background: $white
  color: $black
  padding: $space*4
  .container
    text-align: center
    p, h2
      margin: $space*2

.item-list
  @include distribute
  justify-content: unset
  flex-wrap: wrap
  padding-top: $space*3
  text-align: center
  .sponsor-item
    width: 350px
    height: 200px
    border-right: 1px solid #d5d5d7
    border-bottom: 1px solid #d5d5d7
    &:nth-child(3n+3)
      border-right: none
    &:nth-last-child(-n+3)
      border-bottom: none
    img
      padding: $space*4
      opacity: 0.1
      cursor: pointer
      &:hover
        opacity: 1
        transition: all 0.5s
      

.cta
  padding-top: $space*5
</style>

