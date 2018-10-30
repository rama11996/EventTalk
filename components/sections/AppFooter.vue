<template lang="pug">
section.app-footer
  .container
    .social
      img.logo(src="@/assets/images/logo-big.png")
      h5 eventnov2018@eventtalk.com
      .external
        img(src="@/assets/images/facebook.png")
        img(src="@/assets/images/twitter.png")
        img(src="@/assets/images/instagram.png")
        img(src="@/assets/images/global.png")
        img(src="@/assets/images/be.png")
        img(src="@/assets/images/linkedin.png")
    .venue
      img.location(src="@/assets/images/location.png")
      span Venue Location
      .date
        h4 12-15 November 2018
        h5 358/1, Hosur road, Ayappa garden,Adugodi,Bangalore, Karantaka - 560 030
        h4.direction Get Direction&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-->
        h6.terms Privacy Policy | Terms & Conditions

  h6.rights @2018.All Rights Reserved by eventtalk.com
</template>
<script>
export default {
  data () {
    return {
      externals: [
    
      ]
    }
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'

section.app-footer
  background: $event-lightblue
  color: $white
  padding: $space*4
  .container
    @include spread
  h6.rights
    text-align: center
    padding-top: $space*3


//social
.social
  flex: 1
  .external
    padding-top: $space*2
    img
      margin: $space/2
  

.venue
  flex: 1
  border-left: 1px solid $white
  padding-left: $space*8
  span
    font-size: 2rem
  .date
    h4
      color: $event-actionpink
    h4.direction, h6, h4
      margin-top: $space*2
</style>

