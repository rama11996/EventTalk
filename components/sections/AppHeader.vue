<template lang="pug">
section.app-header(:class="{dark: isScroll}")
  .container
    .logo
      img(src="@/assets/images/logo.png", alt="")
    nav.navigation
      .primary
        a About
        a Agenda
        a Speakers
        a Venue
        a FAQ
      .secondary
        a.btn.small Buy Ticket
</template>


<script>
export default {
  data () {
    return {
      isScroll: false
    }
  },
  created () {
    if (process.client)
      window.addEventListener('scroll', this.handleScroll);
  },
  destroyed () {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll () {
      this.isScroll = window.scrollY >= 60
    }
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'

section.app-header
  background: $event-blue
  color: $white
  @include fixed-n
  .container
    @include spread
    .logo
    .navigation
      @include flex
      .primary a
        margin: $space*2


.app-header.dark
  background: $neutral
  color: $black
  transition: background-color 0.35s, border 0.35s
  position: fixed
  top: 0
  left: 0
  width: 100%
  z-index: 20
</style>
