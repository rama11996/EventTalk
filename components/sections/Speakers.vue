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
          .logos
            img(src="@/assets/images/facebook.png")
            img(src="@/assets/images/twitter.png")
            img(src="@/assets/images/instagram.png")
            img(src="@/assets/images/tripple.png")
          .story
            h5 Story  
            img(src="@/assets/images/arrow.png")
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
  padding: $space*3
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
        position: relative
        .image
          width: 300px
          height: 300px
          background: #666666
          overflow: hidden
          img
            min-width: 300px
            -webkit-filter: grayscale(100%)
            filter: grayscale(100%)
            &:hover
              -webkit-filter: grayscale(100%)
              filter: grayscale(0%)
        .details
          background: #FFFFFF
          height: 150px
          text-align: center
          padding: $space/2
          transition: all 0.5s
          @include absolute
          top: 18rem
          .name
            margin-top: 1.5rem
            font-weight: 700
        .social
          background: $event-hoverpink
          overflow: hidden
          width: 100%
          height: 0px
          transition: all 0.5s
          position: absolute
          bottom: 0
          left: 0
          right: 0
          .logos
            img
              margin: $space/2
        &:hover
          cursor: pointer
          .details
            height: 180px
          .social
            @include flex
            height: 15% 
            padding: 0.5rem
            .story
              @include flex
              color: $white
        

section.speakers
  .container
    .btn
      margin: 0 auto
      display: block
      

      
      
</style>

