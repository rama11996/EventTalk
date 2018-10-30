<template lang="pug">
section.register
  .container
    .content
      h2 Are you ready to learn,connect get inspired and have fun?
      p Event talk is the place for you. Resgister now and grab your seat Hurry , limited seat available
      button.btn.btn-primary Resgister Now
</template>
<script>
export default {
  
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'

section.register
  background: $white
  color: $black
  .container
    .content  
      text-align: center
      h2
        width: 65%
        margin: 0 auto
        margin-top: $space*1.5
        padding: $space*3
      p
        margin: 0 auto
        width: 80%
      button
        margin: $space*3
</style>

