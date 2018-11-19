<template lang="pug">
section.about
  .container
    .content
      h2 About the Event
      p Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock
    ul.items
      li.item(v-for="(a, i) in about", :key="i")
        .thumb
          img(:src="a.image", alt="thumb")
        .item-content
          h3 {{ a.title }}
          p {{ a.content }}
</template>
<script>
export default {
  data () {
    return {
      about: [
        {
          title: 'Guidelines for paper submissions',
          content: 'There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don\'t look even slightly believable. If you are going',
          image: 'images/about1.png'
        },
        {
          title: 'Activites and Structure',
          content: 'All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary, making this the first true generator on the Internet.',
          image: 'images/about2.png'
        }
      ]
    }
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'

section.about
  background: $white
  color: $black
  padding: $space*3
  .content
    text-align: center
    padding: $space*3
p
  color: $neutral-light
  margin-top: $space*2
  line-height: 2rem
 

.item
  @include flex
  @media (max-width: $breakpoint-tab-3)
    flex-direction: column-reverse
  margin-bottom: $space*2
  @media (min-width: $breakpoint-tab-3)
    &:nth-child(odd)
      flex-direction: row-reverse
  .thumb, .item-content
    flex: 1
    text-align: center
  .item-content 
    p
      margin-bottom: $space*2.5

</style>

