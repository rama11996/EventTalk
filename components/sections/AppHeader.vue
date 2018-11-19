<template lang="pug">
section.app-header(:class="{dark: isScroll, open: open}")
  .container
    a.logo(href="#", v-scroll-to="'.hero'")
      img(src="@/assets/images/logo.png", alt="")
    .mask(v-if="open", @click="hide()")
    a.hamburger(@click="toggle()")
      img(v-if="open", src="@/assets/images/close.png")
      img(v-else, src="@/assets/images/menu.png")
    nav.navigation(:class="{open: open}", @click="hide()" )
      .primary
        a(href="#", v-scroll-to="'.about'") About
        a(href="#", v-scroll-to="'.speakers'") Speakers
        a(href="#", v-scroll-to="'.agenda'") Agenda
        a(href="#", v-scroll-to="'.sign-up'") SignUp
        a(href="#", v-scroll-to="'.sponsors'") Sponsors
        a(href="#", v-scroll-to="'.register'") Register
        a(href="#", v-scroll-to="'.app-footer'") Contact
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
    show () {
      this.open = true
    },
    hide () {
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
    .navigation
      position: relative
      @include flex
      .primary a
        margin: $space
        text-decoration: none
        color: $white

.primary
  @media (max-width: $breakpoint-appheader)
    display: none


.app-header.dark
  transition: background-color 0.35s, border 0.35s
  position: fixed
  top: 0
  left: 0
  width: 100%
  z-index: 20


.app-header
  .mask
    @include fixed
    z-index: 1

.app-header
  position: relative
  a.hamburger
    cursor: pointer
    display: block
    @include absolute-e
    margin: $space*1.5
    padding-top: $space*1.5
    @media (min-width: $breakpoint-appheader)
      display: none

.app-header.open
  height: 100vh
  background: $event-blue
  width: 100%
  .mask
    width: 10vw
  .logo
    display: none

.navigation.open
  .primary
    @include flex
    flex-direction: column
    align-items: center
    text-align: center
    @include fixed-s
    bottom: 4rem

// section.app-header
//   .container
//     .menu
//       .navigation
//         @media (max-width: $breakpoint-desktop)
//           flex-direction: column
//           justify-content: flex-start
//           background: $event-blue
//           width: 100%
//           padding-top: $space*4
//           position: fixed
//           right: 0
//           top: 0
//           bottom: 0
//           .primary
            // @include flex
            // flex-direction: column
//             padding: $space
//             a
//               padding: $space
//               font-size: 1.4rem
//     .hamburger
//       display: none
//       position: absolute
//       right: 0
//       cursor: pointer
//       z-index: 20
//       padding: $space*2
//       display: none
//       @media (max-width: $breakpoint-desktop)
//         display: block

//     .menu
//       @media (max-width: $breakpoint-desktop)
//         display: none
//         &.open
          // display: block
          // position: fixed
          // right: 0
          // top: 0
          // bottom: 0

//           .mask
//             position: fixed
//             right: 0
//             top: 0
//             bottom: 0
//             left: 0
</style>
