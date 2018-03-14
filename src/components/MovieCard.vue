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
      <star-rating
        :rating="movie.rating"
        :max-rating="4"
        inactive-color="#dddddd"
        active-color="#b9cb41"
        :star-size="18"
        :read-only="true"
        :show-rating="false"/>

      <div class="share">
        <a href="https://facebook.com.br" target="_blank">
          <img src="../assets/facebook.png" alt="Facebook">
        </a>
      </div>
    </div>
  </li>
</template>

<script>
import StarRating from 'vue-star-rating'

export default {
  name: 'MovieCard',
  props: {
    movie: {
      required: true,
      type: Object
    }
  },
  components: {
    StarRating
  }
}
</script>

<style lang="stylus" scoped>
  .movie-card
    box-shadow 0 0 4px rgba(0, 0, 0, 0.12)
    background #fff
    padding 0 0 50px
    position relative

    &__image
      img
        max-width 100%
        width 100%
        display block
        margin 0 auto

    &__info
      padding 18px

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

    &__highlights
      position absolute
      height 50px
      width 100%
      left 0
      bottom 0
      border-top 1px solid #e8e8e8
      display flex
      flex-flow row wrap
      align-items center
      justify-content space-between

      .vue-star-rating
        margin 0 0 0 15px

      .share
        margin 0 15px 0 0
</style>
