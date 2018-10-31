<template lang="pug">
section.app-header(:class="{dark: isScroll}")
  .container
    a.logo(href="#", v-scroll-to="'.hero'")
      img(src="@/assets/images/logo.png", alt="")
    nav.navigation
      .primary
        a(href="#", v-scroll-to="'.about'") About
        a(href="#", v-scroll-to="'.speakers'") Speakers
        a(href="#", v-scroll-to="'.agenda'") Agenda
        a(href="#", v-scroll-to="'.sign-up'") SignUp
        a(href="#", v-scroll-to="'.sponsors'") Sponsors
        a(href="#", v-scroll-to="'.register'") Register
        a(href="#", v-scroll-to="'.app-footer'") Contact
      .secondary
        a.btn.small(href="#", v-scroll-to="'.tickets'") Buy Ticket
</template>


<script>
import Vue from 'vue'
import vueScrollTo from 'vue-scroll-to'
 
Vue.use(vueScrollTo)
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
        margin: $space
        text-decoration: none
        color: $white


.app-header.dark
  transition: background-color 0.35s, border 0.35s
  position: fixed
  top: 0
  left: 0
  width: 100%
  z-index: 20
</style>
