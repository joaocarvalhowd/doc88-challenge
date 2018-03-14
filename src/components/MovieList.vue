<template>
  <div>
    <container
     v-infinite-scroll="loadMore"
     infinite-scroll-disabled="loading"
     infinite-scroll-distance="300">
      <ul class="movie-list">
        <movie-card
          :movie="movie"
          v-for="(movie, index) in movies"
          :key="index"/>
      </ul>
    </container>
    <container>
      <loading :loading="loading"></loading>
    </container>
  </div>
</template>

<script>
import axios from 'axios'
import paginateArray from 'paginate-array'
import Container from '@/components/Container'
import MovieCard from '@/components/MovieCard'
import Loading from '@/components/Loading'

export default {
  name: 'MovieList',
  data: () => ({
    moviesServer: [],
    currentPage: 1,
    perPage: 12,
    totalPages: null,
    movies: [],
    loading: true
  }),
  methods: {
    async getMovies () {
      const {data: moviesServer} = await axios.get('https://jsonplaceholder.typicode.com/posts')
      const categories = ['Movies', 'Animations', '3D Animations', 'Kids movies']

      this.moviesServer = moviesServer.map(eachItem => {
        return {
          ...eachItem,
          rating: Math.floor((Math.random() * 5)),
          urlImage: `https://via.placeholder.com/640x480`,
          category: categories[Math.floor(Math.random() * categories.length)]
        }
      })

      this.paginateFirstPage()
    },
    paginateFirstPage () {
      setTimeout(() => {
        const {data: movies, currentPage, totaPages} = paginateArray(this.moviesServer, this.currentPage, this.perPage)

        this.currentPage = currentPage
        this.totalPages = totaPages

        this.movies = movies
        this.loading = false
      }, 1500)
    },
    loadMore () {
      if (this.currentPage < this.totalPages) {
        this.loading = true

        setTimeout(() => {
          const {data: movies, currentPage, totaPages} = paginateArray(this.moviesServer, this.currentPage + 1, this.perPage)

          this.currentPage = currentPage
          this.totalPages = totaPages

          this.movies.push(...movies)
          this.loading = false
        }, 1500)
      }
    }
  },
  mounted () {
    this.getMovies()
  },
  components: {
    Container,
    MovieCard,
    Loading
  }
}
</script>

<style lang="stylus" scoped>
  .movie-list
    margin 0
    padding 0
    list-style none
    display flex
    flex-flow row wrap

    @media screen and (min-width: 768px)
      margin 40px 0 0

    .movie-card
      flex 1 0 100%
      margin 0 0 15px

      @media screen and (min-width: 768px) and (max-width: 991px)
        max-width calc(4/12 * 100% - (1 - 4/12)*15px)
        margin 0 15px 15px 0

        &:nth-child(3n)
          margin 0 0 15px

      @media screen and (min-width: 992px)
        max-width calc(3/12 * 100% - (1 - 3/12)*15px)
        margin 0 15px 15px 0

        &:nth-child(4n)
          margin 0 0 15px
</style>
