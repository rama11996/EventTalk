<template lang="pug">
section.app-header(:class="{dark: isScroll, open: open}")
  .container
    a.logo(href="#", v-scroll-to="'.hero'")
      img(src="@/assets/images/logo.png", alt="")
    .mask(v-if="open", @click="hide()")  
    a.hamburger(@click="toggle()")
       img(src="@/assets/images/hamburger.png")    
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
    },
    hide(){
      this.open = true
    },
    show(){
      this.open = false
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

section.app-header
  .container
    
    .navigation
      @media (max-width: $breakpoint-desktop)
        display: none  
    .hamburger
      @media (min-width: $breakpoint-desktop)
        display: none  

</style>
 