<template lang="pug">
section.sign-up
  .container
    .content
      h2 Stay up to date
      p Do you want to stay o the loop and to be notified when we organise another conference meetup?
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
  background: $event-blue
  color: $white
  .container
    .content  
      text-align: center
      padding: $space*2.25
      h2
        width: 65%
        margin: 0 auto
        // margin-top: $space*1.5
        padding-bottom: $space*2
      p
        margin: 0 auto
        width: 45%
        color: $white
        padding-bottom: $space*2
      .btn
        // margin: $space*3
        border-radius: 0 10px 10px 0
        
      input
        padding: $space*1.5 $space*12 $space*1.5 $space
        border-radius: 10px 0 0 10px
        border: none
</style>
