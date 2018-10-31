<template lang="pug">
section.tickets
  .container
    .ticket-content
      h2 Book Your Conference Tickets now !
      .tabs
        a.btn.btn.primary-small Personal
        a.btn.btn.primary-small Company
      p loremcombined with a handful of model sentence structures, to generate Lorem Ipsum which looks reasonable. The generated Lorem Ipsum is therefore always free from repetition, injected humourc
    .pricing
      .price-card(v-for="(p, i) in pricing", :key="i", :class="p.type.toLowerCase()")
        h2 {{ p.type }}
        h4 {{ p.price }}
        ul
          li.feature(v-for="(f, j) in p.features" :key="j") 
            span {{ f }}
        .cta
          a.btn.btn-primary Buy Ticket
</template>
<script>
export default {
  data () {
    return {
      pricing: [
        {
          type: 'Standard',
          price: '$55 month',
          features: [
            'Entrance',
            'Coffe break',
            'One free bonus theme',
            'Freen lunch and snacks',
            'certificate and ebook'
          ]
        },
        {
          type: 'Premium',
          price: '$55 month',
          features: [
            'Entrance',
            'Coffe break',
            'One free bonus theme',
            'Freen lunch and snacks',
            'certificate and ebook'
          ]
        }
      ]
    }
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'

section.tickets
  background: $neutral
  color: $black
  .container
    @include flex

.ticket-content
  width: 30rem
  // flex: 1
  h2
    text-align: left
  .tabs
    margin-top: $space*3
    border: 2px solid $event-blue
    border-radius: 40px
    padding: $space*1.5
    text-transform: normal
    a
      font-size: 1.5rem
      border-radius: 50px
      padding: $space/2 $space*2.5

a
  &:first-child
    margin-right: $space/2
  &:last-child
    margin-left: 0

p
  padding-top: $space*3

.pricing
  flex: 1
  .price-card
    background: $white
    text-align: center
    width: 30rem
    height: 40rem
    margin: 1rem
  h2
    font-weight: normal
    border-bottom: 2px solid $neutral
    padding: $space*2
  h4
    font-size: 1.75rem
    color: $event-actionpink
    border-bottom: 2px solid $neutral
    padding: $space
  .cta
    padding-top: $space*2
  .feature
    text-align: left
    margin: $space*2
    &:before
      content: '\2714'
      color: $event-actionpink
      border: 2px solid $event-actionpink
      border-radius: 50%
      width: 1.5rem
      height: 1.5rem
      display: inline-block
      text-align: center
      margin-right: 2rem

//Animations
.pricing
  position: relative
  height: 60rem
  .price-card
    @include absolute
    &.standard
      z-index: 1
    &.premium
      transform: translateX(20rem)
      opacity: 0.5
      height: 35rem
</style>

