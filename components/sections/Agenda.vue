<template lang="pug">
section.agenda
  .container
    h2 Event Schedule
    p Conference deticated to remarkable events
    .content
      nav
        a.btn.btn-primary(@click="select(i)", v-for="(day, i) in data", :key="i") {{ day.day }}
      .sessions(v-if="selected === i", v-for="(day, i) in data", :key="i")
        .session(v-for="(s, j) in day.session", :key="j")
          .time
            h4 {{ s.start_time }} To {{ s.end_time }}
            h6 {{ s.type }}
          .session-title
            h3 {{ s.title }}
            h6 {{ s.content }}
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
    a
      margin: $space*2
      font-size: 1.75rem !important

.sessions
  margin-top: $space*7
  .session
    padding: $space*3
    @include flex
    border-top: 1px solid #d5d5d7
    h4
      text-align: center
      font-weight: 500
    .session-title
      width: 30rem
      text-align: left
p
  text-align: center
  margin-top: 3rem
</style>

