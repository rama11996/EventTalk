<template lang="pug">
section.sign-up
  .container
    .content
      h2 Stay up to date
      p Do you want to stay o the loop and to be notified when we organise another conference meetup?
      .register
        input(type="text" placeholder="Your email address")
        button.btn Sign Up
</template>
<script>
export default {

}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'

section.sign-up
  background: url(/images/bottom-banner.png)  #310883
  background-size: cover
  background-repeat: no-repeat
  color: $white
  max-width: 100%
  .container
    .content
      text-align: center
      padding: $space*3.5
      h2
        font-weight: 500

        padding-bottom: $space*2
      p
        color: $white
        padding-bottom: $space*2
      .btn
        border-radius: 0 10px 10px 0
        padding: $space*1.2 $space*2.5
        @media (max-width: $breakpoint-tab-1)
          border-radius: 10px
          margin-top: $space*2

      input
        padding: $space*1.8 $space*16 $space*1.5 $space
        border-radius: 10px 0 0 10px
        border: none
        @media (max-width: $breakpoint-tab-1)
          border-radius: 10px
          text-align: center
          margin-left: -2.5rem
</style>
