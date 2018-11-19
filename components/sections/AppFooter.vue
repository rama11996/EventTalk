<template lang="pug">
section.app-footer
  .container
    .social
      img.logo(src="@/assets/images/logo-big.png")
      h5 eventnov2018@eventtalk.com
      .external
        img(src="@/assets/images/facebook1.png")
        img(src="@/assets/images/twitter1.png")
        img(src="@/assets/images/instagram1.png")
        img(src="@/assets/images/global.png")
        img(src="@/assets/images/be.png")
        img(src="@/assets/images/linkedin.png")
    .venue
      .venue-container
        img.location(src="@/assets/images/location.png")
        span Venue Location
        .date
          h5 12-15 November 2018
          h6 358/1, Hosur road, Ayappa garden,Adugodi,Bangalore, Karantaka - 560 030
        .direction
          span.dir Get Direction&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          img(src="@/assets/images/dir.png")
          h6 Privacy Policy | Terms and Conditions
  .copyrights
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
  padding: $space*2
  .container
    @media (min-width: $breakpoint-tab-1)
      @include spread

  .copyrights
    text-align: center
    padding-top: $space*5


// social
.social
  flex: 1
  .external
    padding-top: $space*2
    img
      margin: $space/2


.venue
  flex: 1
  padding-top: $space*4
  text-align: center
  @media (min-width: $breakpoint-tab-3)
    border-left: 1px solid $white
    text-align: left
    .venue-container
      padding-left: $space*12

  span
    font-size: 1.5rem
  .date, .direction
    span, h5
      color: $event-actionpink
    span.dir, h6, h5
      margin-top: $space
    span.dir
      font-size: 1.2rem
</style>

