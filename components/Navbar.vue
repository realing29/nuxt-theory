<template lang='pug'>
  header
    nav.navbar.navbar-expand-lg.navbar-light.bg-light
      a.navbar-brand(href='#') NuxtJS
      .collapse.navbar-collapse
        ul.navbar-nav.mr-auto
          li.nav-item
            nuxt-link.nav-link(active-class='active' exact='' to='/') Home
          li.nav-item
            nuxt-link.nav-link(to='/users') Users
          li.nav-item
            nuxt-link.nav-link(no-prefetch='' to='/about') About
          li.nav-item
            nuxt-link.nav-link(no-prefetch='' to='/login') Login
          li.nav-item(v-if='isAuth')
            a.nav-link(href='#' @click.prevent='logout') Logout

</template>

<script>
export default {
  computed: {
    isAuth(){
      return this.$store.getters.isAuth
    }
  },
  methods: {
    logout(){
      this.$store.dispatch('logout')
    }
  }
}
</script>