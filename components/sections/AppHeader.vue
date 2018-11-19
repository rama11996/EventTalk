<template lang="pug">
section.app-header(:class="{dark: isScroll, open: open}")
  .container
    a.logo(href="#", v-scroll-to="'.hero'")
      img(src="@/assets/images/logo.png", alt="")
    a.hamburger(@click="toggle()"  :class="{open: open}")
       img(src="@/assets/images/hamburger.png") 
    .menu(:class="{open: open}")      
      .mask(@click="toggle()")
      nav.navigation(:class="{open: open}" )
        .primary(:class="{open: open}" )
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
      isScroll: false,
      open: false
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
    },
    toggle(){
      this.open = !this.open
    }
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'
// @mixin full-screen
//   position: fixed
//   right: 0
//   top: 0
//   bottom: 0
//   left: 0
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

section.app-header
  .container
    .navigation
      position: fixed
      top: 5rem
      right: 0rem 
      @media (max-width: $breakpoint-desktop)
        visibility: hidden
        @include flex
        flex-direction: column
        .primary 
          &.open a
            display: block
            color: black
        &.open
          visibility: visible 
    .hamburger
      display: none 
      position: absolute
      right: 0
      font-size: 2rem 
      padding: 0.5rem 0 0 1rem
      cursor: pointer
      z-index: 2
      display: none
      @media (max-width: $breakpoint-desktop)
        display: block




</style>
 