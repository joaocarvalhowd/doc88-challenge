<template>
  <div class="search">
    <div class="icon-mobile">
      <img src="../assets/icon-search.png">
    </div>

    <form>
      <div class="input-group">
        <div class="icon">
          <img src="../assets/icon-search-lg.png">
        </div>
        <input type="search">
      </div>
    </form>
  </div>
</template>

<style lang="stylus" scoped>
  .search
    .icon-mobile
      padding 9px 19px 7px 18px
      background-image linear-gradient(to top, rgba(0, 0, 0, 0.04) 0%, rgba(255, 255, 255, 0.04) 100%)
      border 1px solid #e7e7e7

      @media screen and (min-width: 768px)
        display none

    form
      display none

      @media screen and (min-width: 768px)
        display block

      .input-group
        width 100%
        max-width 100%
        position relative

        .icon
          position absolute
          right 10px
          top 60%
          transform translateY(-50%)
          cursor pointer

        input
          width 100%
          background #f7f6f6
          border 1px solid #e7e7e7
          box-shadow none
          outline none
          padding 6.5px 35px 6.5px 5px
</style>
