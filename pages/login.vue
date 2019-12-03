<template lang='pug'>
  form
    h1 Login
    .form-group
      input.form-control(type='text')
    .form-group
      input.form-control(type='password')
    p
      nuxt-link(to='/') Home
    button.btn.btn-primary Login
</template>

<script>
export default {
  layout: 'empty'
}
</script>

<style lang="stylus">
  form
    width 600px
</style>