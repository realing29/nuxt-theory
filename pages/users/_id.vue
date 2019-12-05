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
  async asyncData({params, error, $axios}){
    try {
      const user = await $axios.$get(`https://jsonplaceholder.typicode.com/users/${params.id}`)
      return {user}
    } catch (e) {
      error(e)
    }
  }
}
</script>