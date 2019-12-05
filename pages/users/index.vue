<template lang='pug'>
  section
    h1 {{pageTitle}}
    ul
      li(v-for='user of users' :key='user.id')
        a(href='#' @click.prevent='goTo(user)') {{user.name}} ({{user.email}})
</template>
<script>
export default {
  asyncData({$axios, error}) {
    return $axios.$get('https://jsonplaceholder.typicode.com/users')
    .then(users => {
      return {
        users
      }
    })
    .catch(err => {
      error(err)
    })
  },
  data: () => ({
    pageTitle: 'User page'
  }),
  methods: {
    goTo(user){   
      this.$router.push('/users/' + user.id)
    }
  }
};
</script>