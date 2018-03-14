<template>
  <div class="loading" v-if="loading">
    <pulse-loader :loading="loading" size="10px" color="#e77161"></pulse-loader>
    <span class="text">Loading page</span>
  </div>
</template>

<script>
import PulseLoader from 'vue-spinner/src/PulseLoader.vue'

export default {
  name: 'Loading',
  props: {
    loading: {
      type: Boolean
    }
  },
  components: {
    PulseLoader
  }
}
</script>

<style lang="stylus" scoped>
  .loading
    text-align center
    padding 20px 0

    .v-spinner
      display inline-block

    span
      margin 0 0 0 15px
      font-size 16px
      font-weight 600
</style>
