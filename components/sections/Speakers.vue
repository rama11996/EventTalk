<template lang="pug">
section.speakers
  .container
    .content
      h2 Who's Speaking?
      p  In publishing and graphic design, lorem ipsum is a placeholder text used 
    .profile
      .card(v-for="speaker in speakers")
        .image
          img(:src="speaker.image")
        .details
          h4.name {{ speaker.name }}
          p {{ speaker.company }}
        .social
          img(src="@/assets/images/facebook.png")
          img(src="@/assets/images/twitter.png")
          img(src="@/assets/images/Instagram.png")

    button.btn.btn-primary View All Speakers


</template>
<script>
export default {
  data() {
    return{
    speakers:[
      {image:'images/speaker-1.jpg', name:'Manuel Neuer',company:'CEO,Spinboard'},  
      {image:'images/speaker-2.jpg', name:'Toni Duggon',company:'GM,Pixelperfect'},
      {image:'images/speaker-3.jpg', name:'Harman Kardon',company:'CEO,Mockplus'}
  ]
 }
}
  
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'

section.speakers
  background: url(/assets/images/speakers-banner.png) $neutral
  background-size: contain
  background-repeat: no-repeat
  min-height: 100vh
  color: $black
  .container
    .content
      text-align: center

section.speakers
  .container
    .profile
      @include distribute
      margin: $space*3 0
      .card
        width: 300px
        height: 450px
        .image
          width: 300px
          height: 300px
          background: #666666
          overflow: hidden
          img
            min-width: 300px
        .details
          background: #FFFFFF
          height: 100px
          text-align: center
          padding: $space/2
          .name
            font-weight: 700
        .social
          padding:  $space
          background: $event-hoverpink
          display: none
          img
            width: 30px    
          
section.speakers
  .container
    .btn
      margin: 0 auto
      display: block
      

      
      
</style>

