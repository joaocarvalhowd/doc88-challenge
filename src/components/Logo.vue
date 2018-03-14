<template>
  <div class="logo">
    <img src="./../assets/logo.png">
  </div>
</template>

<script>
export default {
  name: 'Logo'
}
</script>

<style lang="stylus" scoped>
  .logo
    img
      display block
      max-width 100%

      @media screen and (min-width: 768px)
        max-width 154px
</style>
