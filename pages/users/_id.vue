<template lang='pug'>
  div
    h1 {{user.name}}
    hr
    b {{user.email}}
</template>
<script>
import { resolve } from 'q'
export default {
  validate({params}){
// проверка валидации на число
    return /^\d+$/.test(params.id)
  },
  async asyncData({params, error, store}){
    try {
      const user = await store.dispatch('users/fetchUserById', params.id)
      return {user}
    } catch (e) {
      error(e)
    }
  }
}
</script>