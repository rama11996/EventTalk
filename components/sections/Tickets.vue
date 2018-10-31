<template lang="pug">
section.tickets
  .container
    .ticket-content
      h2 Book Your Conference Tickets now !
      .tabs
        a.btn(
          :class="{'primary-small': active === 'Standard'}"
          @click="activate('Standard')") 
          | Standard
        a.btn(
          :class="{'primary-small': active === 'Premium'}"
          @click="activate('Premium')") 
          | Premium
      p loremcombined with a handful of model sentence structures, to generate Lorem Ipsum which looks reasonable. The generated Lorem Ipsum is therefore always free from repetition, injected humourc
    .pricing
      .price-card(v-for="(p, i) in pricing", :key="i", :class="{active: active === p.type}")
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
      active: 'Standard',
      pricing: [
        {
          type: 'Standard',
          price: '$199 month',
          features: [
            'Entrance',
            'Coffe break',
            'Free lunch and snacks',
          ]
        },
        {
          type: 'Premium',
          price: '$299 month',
          features: [
            'Entrance',
            'Coffe break',
            'One free bonus theme',
            'Free lunch and snacks',
            'certificate and ebook'
          ]
        }
      ]
    }
  },
  methods: {
    activate (type) {
      this.active = type
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
    overflow: visible


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
    a.btn
      font-size: 1.5rem
      border-radius: 50px
      padding: $space/2 $space*2.5
      background: none
      color: $event-blue
      border-color: transparent
      &.primary-small
        background: $event-blue
        color: $white
a
  &:first-child
    margin-right: $space/2
  &:last-child
    margin-left: 0

p
  padding-top: $space*3

.pricing
  flex: 1
  overflow: visible
  .price-card
    background: $white
    text-align: center
    width: 25rem
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

@keyframes activate
  0%
    opacity: 0.5
    transform: translateX(15rem) scale(0.9)
  50% 
    opacity: 1
    transform: translateX(20rem) scale(1)
  100%
    opacity: 1
    transform: translateX(0) scale(1)

@keyframes deactivate
  0%
    opacity: 1
    transform: translateX(0) scale(1)
  50% 
    opacity: 1
    transform: translateX(-5rem) scale(0.9)
  100%
    opacity: 0.5
    transform: translateX(15rem) scale(0.9)



.pricing
  position: relative
  height: 60rem
  .price-card
    @include absolute
    box-shadow: 0 0 25px 5px rgba($black, 0.1)
    animation: deactivate 1s ease-in-out
    transform: translateX(15rem) scale(0.9)
    z-index: 1
    opacity: 0.5
    &.active
      animation: activate 1s ease-in-out
      transform: translateX(0) scale(1)
      z-index: 2
      opacity: 1
</style>

