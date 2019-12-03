<template lang='pug'>
  section
    h1 Error 404
    nuxt-link(:to="'/'") Home
</template>
<style scoped lang="stylus">
  h1
    color red
  section
    display flex
    align-items center
    flex-direction column
</style>