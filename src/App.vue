<template>
  <div id="app">
    <app-header/>

    <router-view/>
  </div>
</template>

<script>
import AppHeader from '@/components/AppHeader'

export default {
  name: 'App',
  components: {
    AppHeader
  }
}
</script>

<style lang="stylus">
@import url('https://fonts.googleapis.com/css?family=Open+Sans')

html, body
  margin 0
  padding 0
  box-sizing border-box

  @media screen and (min-width: 768px)
    background #f0efee

#app
  font-family 'Open Sans', sans-serif
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
</style>
