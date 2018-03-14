<template>
  <header class="app-header">
    <container>
      <div class="app-header__content">
        <navigation-menu/>

        <logo/>

        <search/>

        <user-account/>
      </div>
    </container>
  </header>
</template>

<script>
import Container from '@/components/Container'
import Logo from '@/components/Logo'
import UserAccount from '@/components/UserAccount'
import NavigationMenu from '@/components/Menu'
import Search from '@/components/Search'

export default {
  name: 'AppHeader',
  components: {
    Container,
    Logo,
    UserAccount,
    NavigationMenu,
    Search
  }
}
</script>

<style lang="stylus" scoped>
  .app-header
    padding 50px 0 40px

    @media screen and (min-width: 768px)
      background #fff
      border 1px solid #d2d1d0
      padding 28px 0 16px

    &__content
      display flex
      flex-flow row wrap
      align-items center
      justify-content space-between

      @media screen and (min-width: 768px)
        .logo
          flex 1 0 auto
          order 1

        .navigation-menu
          flex 1 0 auto
          order 2

        .search
          flex 2 0 auto
          order 3

        .user-account
          flex 1 0 auto
          order 4
</style>
