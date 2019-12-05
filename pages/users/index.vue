<template lang='pug'>
  section
    h1 {{pageTitle}}
    ul
      li(v-for='user of users' :key='user.id')
        a(href='#' @click.prevent='goTo(user)') {{user.name}} ({{user.email}})
</template>
<script>
export default {
  async asyncData({store, error}) {
    try{
      const users = await store.dispatch('users/fetchUsers')
      return {users}
    } catch (e){
      error(e)
    }
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