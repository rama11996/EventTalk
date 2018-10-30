<template lang="pug">
.page
  Appheader
  Hero
  About
  Speakers
  Agenda
  SignUp
  Sponsors
  Tickets
  Register
  AppFooter
</template>

<script>
import Appheader from '@/components/sections/Appheader'
import Hero from '@/components/sections/Hero'
import About from '@/components/sections/About'
import Speakers from '@/components/sections/Speakers'
import Agenda from '@/components/sections/Agenda'
import SignUp from '@/components/sections/SignUp'
import Sponsors from '@/components/sections/Sponsors'
import Tickets from '@/components/sections/Tickets'
import Register from '@/components/sections/Register'
import AppFooter from '@/components/sections/AppFooter'
export default {
  components: {
  Appheader,
  Hero,
  About,
  Speakers,
  Agenda,
  SignUp,
  Sponsors,
  Tickets,
  Register,
  AppFooter
  }
}
</script>


<style lang="sass" scoped>
@import 'assets/styles/includes'
</style>
