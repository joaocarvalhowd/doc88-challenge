<template>
  <div class="user-account">
    <div class="user-account__image">
      <img src="../assets/user-icon.png" alt="Welcome John">
    </div>
    <div class="user-account__name">
      Welcome John
    </div>
  </div>
</template>

<style lang="stylus" scoped>
  .user-account
    display none
    flex-flow row wrap
    justify-content flex-end
    align-items center

    @media screen and (min-width: 768px)
      display flex

    &__image
      margin 0 10px 0 0

    &__name
      font-size 15px
      line-height 16px
      color #8c8c8c
</style>
