<template lang="pug">
section.hero
  AppHeader
  .container
    .content
      h2 Freelancers
      h1 Conferences 2018
      h5 12 - 15 November with over 20 sessions - Bangalore,India
      .cta
        a.btn Register Now
    .image
      img(src="@/assets/images/hero.png")
</template>

<script>
import AppHeader from '@/components/sections/AppHeader'
export default {
  components: {
    AppHeader
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'

section.hero
  background: url(/static/images/herobanner.png) $event-blue
  background-size: contain
  background-repeat: no-repeat
  color: $white
  min-height: 100vh
  padding-top: $space*9
  .container
    text-align: center
    @media (min-width: $breakpoint-tab-1)
      @include spread
      text-align: left
    .image
      margin-top: $space*6
      img
        max-width: 100%
    .cta
      margin-top: $space*6

h2
  text-align: center
  font-size: 3rem
  font-weight: normal
  @media (min-width: $breakpoint-tab-1)
    text-align: left
h1
  @media (max-width: $breakpoint-tab-1)
    font-size: 3rem

</style>
