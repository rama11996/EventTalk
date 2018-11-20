<template lang="pug">
section.agenda
  .container
    h2 Event Schedule
    p Conference deticated to remarkable events
    .content
      nav
        a.btn(@click="select(i)", v-for="(day, i) in data", :key="i", :class="{'btn-primary': selected === i }") {{ day.day }}
      .sessions(v-if="selected === i", v-for="(day, i) in data", :key="i")
        .session(v-for="(s, j) in day.session", :key="j")
          .time
            h4 {{ s.start_time }} To {{ s.end_time }}
            h6 {{ s.type }}
          .session-title
            h3 {{ s.title }}
            p {{ s.content }}
          .session-speaker
            img(v-if="s.image", :src="s.image")
</template>

<script>
import session from './sessions'
export default {
  data () {
    return {
      data: session,
      selected: 0
    }
  },
  methods: {
    select (i) {
      this.selected = i
    }
  }
}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'

section.agenda
  background: $white
  color: $black
  padding: $space*3
.content
  nav
    margin-top: $space*5
    text-align: center
    a.btn
      margin: $space*2
      font-size: 1.75rem !important
      padding: $space/2 $space*2.5
      background: none
      color: #656565
      border-color: transparent
      @media (max-width: $breakpoint-tab-1)
        padding: $space/2
        font-size: 0.25rem !important
        width: 100%
        margin: 0.125rem
      &.btn-primary
        background: $event-blue
        color: $white

.sessions
  margin-top: $space*7
  @media (max-width: $breakpoint-tab-1)
    margin-top: $space*4
  .session
    padding: $space*3
    @include flex
    @media (min-width: $breakpoint-tab-1)
      border-top: 1px solid #d5d5d7
    @media (max-width: $breakpoint-tab-1)
      display: block
      padding: 0
      border: 1px dotted #d5d5d7
    h4
      text-align: center
      font-weight: 500
      @media (max-width: $breakpoint-tab-1)
        text-align: left
        font-weight: 400
    .time
      @media (max-width: $breakpoint-tab-1)
        background: $event-blue
        color: $white
        margin: 0
        padding: $space
    .session-title
      width: 30rem
      text-align: left
      > p
        text-align: left
        margin-top: $space
      @media (max-width: $breakpoint-tab-1)
        width: 100%
        padding: $space*2
        h3
          font-size: 1.5rem !important
        p
          white-space: normal
          word-break: break-all
p
  text-align: center
  margin-top: 3rem

.session-speaker
  @media (max-width: $breakpoint-tab-1)
    img
      display: none
</style>

