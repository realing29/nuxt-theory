<template lang='pug'>
  form(@submit.prevent='onSubmit')
    h1 Login
    .form-group
      input.form-control(type='text')
    .form-group
      input.form-control(type='password')
    p
      nuxt-link(to='/') Home
    button.btn.btn-primary(type='submit') Login
</template>

<script>
export default {
  layout: 'empty',
  methods:{
    onSubmit(){
      this.$store.dispatch('login')
      this.$router.push('/')
    }
  }
}
</script>

<style lang="stylus">
  form
    width 600px
</style>