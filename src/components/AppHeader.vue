<template>
  <header class="app-header">
    <container>
      <div class="app-header__content">
        <logo/>
      </div>
    </container>
  </header>
</template>

<script>
import Container from '@/components/Container'
import Logo from '@/components/Logo'

export default {
  name: 'AppHeader',
  components: {
    Container,
    Logo
  }
}
</script>

<style lang="stylus" scoped>
  header
    padding 50px 0 40px

    @media screen and (min-width: 768px)
      background #fff
      border 1px solid #d2d1d0
      padding 28px 0 16px
</style>
