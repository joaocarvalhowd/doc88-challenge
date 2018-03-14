<template>
  <li class="movie-card">
    <div class="movie-card__image">
      <img :src="movie.urlImage" :alt="movie.title">
    </div>

    <div class="movie-card__info">
      <h2>{{ movie.title }}</h2>
      <p>{{ movie.body }}</p>
    </div>

    <div class="movie-card__highlights">

    </div>
  </li>
</template>

<script>
export default {
  name: 'MovieCard',
  props: {
    movie: {
      required: true,
      type: Object
    }
  }
}
</script>

<style lang="stylus" scoped>
  .movie-card
    box-shadow 0 0 4px rgba(0, 0, 0, 0.12)
    background #fff
    margin 0 0 15px

    &__image
      img
        max-width 100%
        width 100%
        display block
        margin 0 auto

    &__info
      padding 18px
      border-bottom 1px solid rgba(0, 0, 0, 0.22)

      h2
        font-size 26px
        line-height 27px
        color #717171

        @media screen and (min-width: 768px)
          font-size 18px
          line-height 27px

      p
        font-size 13px
        color #acaaaa
        margin 0 0 18px
        line-height 19px

        @media screen and (min-width: 768px)
          line-height 16px


</style>
