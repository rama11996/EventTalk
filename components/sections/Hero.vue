<template lang="pug">
section.hero
  AppHeader
  .container
    .content
      h2 Freelancers 
      h1 Conferences 2018
      h5 12 - 15 November with over 20 sessions-Bangalore, India
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
  background: url(/assets/images/hero-banner.png) $event-blue
  background-size: contain
  background-repeat: no-repeat
  color: $white
  min-height: 100vh
  padding-top: $space*10
  .container
    @include spread
    .content
      text-align: left
      .cta
        margin-top: $space*6
h2
  text-align: left
  font-size: 3.5rem
  font-weight: normal

</style>
